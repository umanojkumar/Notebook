import java.util.concurrent.*;

class Worker implements Callable<Integer> {
    private final int taskId;

    public Worker(int taskId) {
        this.taskId = taskId;
    }

    @Override
    public Integer call() {
        return processLoop();
    }

    private int processLoop() {
        return taskId; // Returning the task ID as required
    }
}

public class ThreadManager {
    public static void wrapperProcess() {
        ExecutorService executor = Executors.newFixedThreadPool(100);
        List<Future<Integer>> futures = new ArrayList<>();

        for (int i = 1; i <= 100; i++) {
            futures.add(executor.submit(new Worker(i)));
        }

        for (Future<Integer> future : futures) {
            try {
                System.out.println("Task ID: " + future.get());
            } catch (InterruptedException | ExecutionException e) {
                e.printStackTrace();
            }
        }

        executor.shutdown();
    }

    public static void main(String[] args) {
        wrapperProcess();
    }
}











Worker Class (Handles Individual Tasks)
import java.util.concurrent.*;


- This imports the Java Concurrency package, which contains utilities for multithreading.

class Worker implements Callable<Integer> {


- Defines the Worker class that implements the Callable<Integer> interface.
- Unlike Runnable, Callable returns a value.

    private final int taskId;


- Declares taskId as final, meaning it won’t change once assigned.

    public Worker(int taskId) {
        this.taskId = taskId;
    }


- This is the constructor, which initializes the worker with a specific taskId.

    @Override
    public Integer call() {
        return processLoop();
    }


- The call() method is the entry point for each thread.
- Calls processLoop(), which returns the task ID.

    private int processLoop() {
        return taskId; // Returning the task ID
    }


- processLoop() simply returns the task ID, representing the unique task each thread executes.


ThreadManager Class (Manages Thread Execution)
public class ThreadManager {


- Declares ThreadManager, the main class responsible for creating and managing threads.

    private static final int THREAD_COUNT = 100;


- Defines a constant THREAD_COUNT, making it easier to modify the number of threads.

    public static void wrapperProcess() {


- wrapperProcess() is the method that manages 100 threads.

        ExecutorService executor = Executors.newFixedThreadPool(THREAD_COUNT);


- Creates a fixed thread pool with THREAD_COUNT (100).
- An ExecutorService manages a pool of worker threads efficiently.

        List<Future<Integer>> taskResults = new ArrayList<>();


- Creates a list to store future results (task IDs returned by threads).

        for (int i = 1; i <= THREAD_COUNT; i++) {
            taskResults.add(executor.submit(new Worker(i)));
        }


- Loop creates and submits 100 threads using executor.submit(new Worker(i)).
- Each thread gets assigned a unique taskId.

        taskResults.forEach(future -> {


- Iterates through the list of Future<Integer> objects.

            try {
                System.out.println("Task ID: " + future.get());
            } catch (InterruptedException | ExecutionException e) {
                Thread.currentThread().interrupt(); // Restore the interrupt status
                System.err.println("Error processing task: " + e.getMessage());
            }


- Retrieves the task ID from each Future<Integer>.
- Handles exceptions properly:- If interrupted, it restores the interrupt status to prevent unexpected behavior.
- Prints an error message if an exception occurs.


        executor.shutdown();


- Shuts down the thread pool after execution, preventing resource leaks.


Main Method (Entry Point)
    public static void main(String[] args) {
        wrapperProcess();
    }


- Executes wrapperProcess(), initiating the threading process.


Final Thoughts
✅ Uses Callable to allow threads to return values.
✅ Uses ExecutorService for efficient thread management.
✅ Implements exception handling to prevent unexpected issues.
✅ Uses constants for cleaner and scalable code.
