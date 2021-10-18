# Methods
package com.company;

public class Main {
    public static void main(String[] args) {

        System.out.println("----------------1----------------");
        char[] chars = new char[]{'a', 'b', 'c'};
        printChars(chars);

        System.out.println("----------------2----------------");
        int[] array2 = new int[]{1, 2, 3, 5, 48, 71};
        char[] result = convertInt(array2);
        System.out.println(result);

        System.out.println("----------------3----------------");
        System.out.println(max(9, 4));

        System.out.println("----------------4----------------");
        System.out.println(max(10, 47, 87));

        System.out.println("----------------5----------------");
        System.out.println(max(10, 14, 7, 8, 12));

        System.out.println("----------------6----------------");
        System.out.println(stringFromChars(new char[]{'a', 'b'}));

        System.out.println("----------------8----------------");
        int[] array8 = new int[]{1, 2, 3, 2, 3, 1};
        int result8 = indexOfValueFromStart(array8, 3);
        System.out.println(result8);

        System.out.println("----------------9----------------");
        int[] array9 = new int[]{1, 2, 3, 2, 3, 1};
        int result9 = indexOfValueFromEnd(array9, 3);
        System.out.println(result9);

        System.out.println("----------------10----------------");
        int result10 = factorial(5);
        System.out.println(result10);

        System.out.println("----------------11----------------");
        boolean result11 = isLeapYear(2000);
        System.out.println(result11);

        System.out.println("----------------12----------------");
        int[] array12 = new int[]{1, 2, 3, 5, 48, 71};
        printAliquotNumbers(array12, 3);

        System.out.println("----------------13----------------");
        int[] result13 = bubbleSort(new int[]{4, 3, 2, 5, 1});
        for (int value : result13) {
            System.out.format("%d ", value);
        }
        System.out.println("");

        System.out.println("----------------14----------------");
        byte[] array14 = new byte[]{1, 2, 3, 5, 2};
        boolean result14 = hasSameBytes(array14);
        System.out.println(result14);

        System.out.println("----------------15----------------");
        int[] arrayA15 = new int[]{1, 2, 3, 4};
        int[] arrayB15 = new int[]{1, 2, 2, 5};
        int[] result15 = multiplyArrays(arrayA15, arrayB15);
        for (int value : result15) {
            System.out.format("%d ", value);
        }
        System.out.println("");

        System.out.println("----------------16----------------");
        int[] arrayA16 = new int[]{1, 2, 3, 4};
        int[] arrayB16 = new int[]{1, 2, 2, 5};
        arrayOfDifferentValues(arrayA16, arrayB16);

        System.out.println("----------------17----------------");
        int[] result17 = revert(new int[]{1, 2, 3, 4, 5});
        for (int value : result17) {
            System.out.format("%d ", value);
        }
        System.out.println("");

        System.out.println("----------------18----------------");
        int[] result18 = random(10, 4, 7);
        for (int value : result18) {
            System.out.format("%d ", value);
        }
        System.out.println("");

        System.out.println("----------------19----------------");
        boolean result19 = contains(new char[]{'a', 'b', 'c', 'd'}, new char[]{'b', 'c'});
        System.out.println(result19);
    }

    // 1) принимает массив чаров, выводит его на экран
    public static void printChars(char[] chars) {
        System.out.println(chars);
    }

    // 2) принимает массив интов, возвращает массив чаров, каждый символ в позиции массива соответствует коду символа передаваемого инта
    public static char[] convertInt(int[] numbers) {
        char[] chars = new char[numbers.length];
        for (int i = 0; i < numbers.length; i++) {
            chars[i] = (char) (numbers[i] + '0');
        }
        return chars;
    }

    // 3) приминает 2 инта, а и б, возвращает большее их этих 2х чисел
    public static int max(int a, int b) {
        if (a < b) {
            return b;
        } else {
            return a;
        }
    }

    // 4) принимает 3 инта, возвращает большее из них
    public static int max(int a, int b, int c) { //1 6 3
        int max = max(a, b); // 1 6 = 6
        max = max(max, c); //6 3
        return max; // 6
    }

    // 5) приминает 5 интов, возвращает большее из них
    static int max(int a, int b, int c, int d, int e) {
        int max = max(a, b, c);
        return max(max, d, e);
    }

    // 6) принимает массив чаров, возвращает строку состоящую из символов массива
    static String stringFromChars(char[] chars) {
        StringBuilder sb = new StringBuilder();
        for (int i = 0; i < chars.length; i++) {
            sb.append(chars[i]);
        }
        return sb.toString();
    }

    // 8) принимает массив интов, и значение типа инт, возвращает индекс массива в котором значение совпадает с передаваемым, начиная с начала массива. Если значения в массиве нет возвращает -1
    static int indexOfValueFromStart(int[] array, int value) {
        for (int i = 0; i < array.length; i++) {
            if (array[i] == value) {
                return i;
            }
        }
        return -1;
    }

    // 9) принимает массив интов, и значение типа инт, возвращает индекс массива в котором значение совпадает с передаваемым, начиная с конца массива. Если значения в массиве нет возвращает -1
    static int indexOfValueFromEnd(int[] array, int value) {
        for (int i = array.length - 1; i >= 0; i--) {
            if (array[i] == value) {
                return i;
            }
        }
        return -1;
    }

    // 10) метод принимает инт, и возвращает факториал от заданого инта
    static int factorial(int value) {
        int result = 1;
        for (int i = 1; i <= value; i++) {
            result = result * i;
        }
        return result;
    }

    // 11) принимает инт год, и возвращает тру если год высокосный
    static boolean isLeapYear(int year) {
        if (year % 4 != 0) {
            return false;
        } else if (year % 400 == 0) {
            return true;
        } else if (year % 100 == 0) {
            return false;
        } else {
            return true;
        }
    }

    // 12) приминает массив интов и число, выводит на екран только елементы массива которые кратны этому числу
    static void printAliquotNumbers(int[] array, int value) {
        for(int i = 0; i < array.length; i ++){
            if(array[i] % value == 0){
              System.out.println(array[i]);
            }
        }
    }

    // 13) метод принимает массив интов сортирует его по возрастанию
        public static int[] bubbleSort(int[] arr){
            for(int i = arr.length-1 ; i > 0 ; i--){
                for(int j = 0 ; j < i ; j++){

            if( arr[j] > arr[j+1] ){
                int tmp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = tmp;
            }
        }
    }
            return arr;
        }

    // 14) принимает массив байт, если в массиве есть повторяющиеся елементы, возвращает тру
    static boolean hasSameBytes(byte[] array) {
        for (int i = 0; i < array.length; i++) {
            for (int j = i + 1; j < array.length; j++) {
                if (array[i] == array[j]) {
                    return true;
                }
            }
        }
        return false;
    }

    // 15) принимает два массива интов одинаковых по длинне, возращает массив интов который состоит из перемноженных елементов входящих массивов
    static int[] multiplyArrays(int[] arrayA, int[] arrayB) {
        int[] result = new int[arrayA.length];
        for(int i = 0; i < arrayA.length; i++)
          result[i] = arrayA[i] * arrayB[i];
        return result;
    }

    // 16) принимает два массива интов, возвращает массив из елементов которые не совпадают в массивах
    static void arrayOfDifferentValues(int[] arrayA, int[] arrayB) {
        for(int i = 0; i < arrayA.length; i++) {
            if (arrayA[i] != arrayB[i]) {
                System.out.println(arrayA[i]);
                System.out.println(arrayB[i]);
            }
        }
    }

    // 17) принимает масив интов, возвращает его же но в реверсном порядке
    static int[] revert(int[] array) {
        for (int i = 0; i < array.length / 2; i++) {
            int leftValue = array[i];
            int rightIndex = array.length - i - 1;
            array[i] = array[rightIndex];
            array[rightIndex] = leftValue;
        }
        return array;
    }

    // 18) принимает 3 инта:
    //  - размер выходного массива
    //  - нижняя граница
    //  - верхняя граница
    // возвращает массив интов заданой длинный, который содержит случайные числа от нижней границы до верхней границы"
    static int random(int min, int max) {
        int range = (max - min) + 1;
        return (int) (Math.random() * range) + min;
    }

    static int[] random(int size, int min, int max) {
        int[] result = new int[size];
        for (int i = 0; i < size; i++) {
            result[i] = random(min, max);
        }
        return result;
    }

    // 19) принимает 2 массива чаров, проверяет есть ли в 1 массиве, такая же последовательность символов которую представляет собой второй массив. Возвращает булеан
    static boolean contains(char[] chars, char[] pattern) {
        int patternIndex = 0;
        for (int i = 0; i < chars.length; i++) {
            if (chars[i] == pattern[patternIndex]) {
                patternIndex++;
            } else {
                patternIndex = 0;
            }
            if (patternIndex == pattern.length) {
                return true;
            }
        }
        return false;
    }
}
