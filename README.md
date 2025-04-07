import org.springframework.web.reactive.function.client.WebClient;
import reactor.core.publisher.Mono;

public class OctaneClient {
    private final WebClient webClient;
    private final String octaneUrl = "https://<octane-server>";
    private String authCookie;

    public OctaneClient() {
        this.webClient = WebClient.builder()
                .baseUrl(octaneUrl)
                .build();
    }

    public void authenticate(String clientId, String clientSecret) {
        String authEndpoint = "/authentication/sign_in";

        // Make the POST request to authenticate
        Mono<String> authResponse = webClient.post()
                .uri(authEndpoint)
                .bodyValue(String.format("{\"client_id\": \"%s\", \"client_secret\": \"%s\"}", clientId, clientSecret))
                .retrieve()
                .bodyToMono(String.class);

        // Extract the authentication cookie
        authResponse.subscribe(response -> {
            // Example: extract auth cookie from headers (simplified for demo purposes)
            authCookie = webClient.get()
                    .uri(authEndpoint)
                    .exchangeToMono(client -> Mono.just(client.cookies().toString()))
                    .block();
            System.out.println("Authenticated successfully!");
        });
    }

    public void fetchWorkspaces(String sharedSpaceId) {
        String workspaceEndpoint = "/api/shared_spaces/" + sharedSpaceId + "/workspaces";

        // Make GET request to fetch workspaces
        Mono<String> workspaceResponse = webClient.get()
                .uri(workspaceEndpoint)
                .header("Cookie", authCookie) // Attach the authentication cookie
                .retrieve()
                .bodyToMono(String.class);

        workspaceResponse.subscribe(workspaces -> {
            System.out.println("Workspaces: " + workspaces);
        });
    }

    public static void main(String[] args) {
        OctaneClient client = new OctaneClient();
        client.authenticate("<your_client_id>", "<your_client_secret>");
        client.fetchWorkspaces("<shared_space_id>");
    }
}
