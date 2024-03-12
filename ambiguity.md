int count = 0;
myfunction(++count, count);



import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReentrantLock;

public class DataProcessor {
    private static final Lock lock = new ReentrantLock();
    private static int data = 0;

    public static void main(String[] args) {
        Thread dataUpdaterThread = new Thread(() -> {
            for (int i = 0; i < 1000; i++) {
                updateData();
            }
        });

        Thread dataReaderThread = new Thread(() -> {
            for (int i = 0; i < 1000; i++) {
                readData();
            }
        });

        dataUpdaterThread.start();
        dataReaderThread.start();
    }

    private static void updateData() {
        lock.lock();
        try {
            // Simulate some processing
            int newData = data + 1;
            try {
                Thread.sleep(10);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            data = newData;
        } finally {
            lock.unlock();
        }
    }

    private static void readData() {
        lock.lock();
        try {
            // Simulate some processing
            int currentData = data;
            try {
                Thread.sleep(10);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            System.out.println("Current data: " + currentData);
        } finally {
            lock.unlock();
        }
    }
}
