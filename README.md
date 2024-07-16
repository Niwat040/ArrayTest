import java.util.Random;

public class ArrayTest2 {
    public static void main(String[] args) {
        int[][] array1 = new int[3][3]; //เป็นการสร้างตัวเเปลที่เป็นตัวเเปล 2 มิติ
        int[][] array2 = new int[3][3];
        Random random = new Random();

        for (int i = 0; i < 2; i++){
            for (int j = 0; j < array1[0].length; j++) {
                array1[i][j] = random.nextInt(100) + 1;
                array2[i][j] = random.nextInt(100) + 1;
            }
        }
        
        
        System.out.println("อาร์เรย์ 1:");
        printArray(array1);

        System.out.println("อาร์เรย์ 2:");
        printArray(array2);
        
        //บรรทัดนี้มีหน้าที่เรียกใช้เมธอดต่างๆและคำนวณ
        add(array1, array2);
        subtract(array1, array2);
        multiply(array1, array2);
        divide(array1, array2);
        modulus(array1, array2);
    }
      // เมธอดของบวก
    public static void add(int[][] array1, int[][] array2) {
        int[][] result = new int[3][3];
        for (int j = 0; j < array1[0].length; j++){
            result[2][j] = array1[1][j] + array2[1][j];
        }
        System.out.println("\nผลลัพท์ (บวก):");
        printArray(result);
    }
       // เมธอดของลบ
    public static void subtract(int[][] array1, int[][] array2) {
        int[][] result = new int[3][3];
        for (int j = 0; j < array1[0].length; j++) {
            result[2][j] = array1[1][j] - array2[1][j];
        }
        System.out.println("\nผลลัพท์ (ลบ):");
        printArray(result);
    }
       // เมธอดของคูณ
    public static void multiply(int[][] array1, int[][] array2) {
        int[][] result = new int[3][3];
        for (int j = 0; j < array1[0].length; j++) {
            result[2][j] = array1[1][j] * array2[1][j];
        }
        System.err.println("\nผลลัพท์ (คูณ):");
        printArray(result);
    }
        // เมธอดของหาร
    public static void divide(int[][] array1, int[][] array2) {
        int[][] result = new int[3][3];
        for (int j = 0; j < array1[0].length; j++) {
            if (array2[1][j] != 0) {
                result[2][j] = array1[1][j] / array2[1][j];
            } else {
                result[2][j] = 0;
            }
        }
        System.out.println("\nผลลัพท์ (หาร):");
        printArray(result);
    }
    // เมธอดของมอด
    public static void modulus(int[][] array1, int[][] array2) {
        int[][] result = new int[3][3];
        for (int j = 0; j < array1[0].length; j++) {
            if (array2[1][j] != 0){
                result[2][j] = array1[1][j] % array2[1][j];
            } else {
                result[2][j] = 0;
            }
        }
        System.out.println("\nผลลัพท์ (มอด)):");
        printArray(result);
    }
    
    public static void printArray(int[][] array) {
        for (int[] row : array){
            for (int value : row){
                System.out.println(value +" ");
            }
            System.out.println();
        }
    }

}
