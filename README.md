Семинар 2 Дз 2
```java
package java_program;

public class program2 {
    static StringBuilder tmp = new StringBuilder();
    public static void main(String[] args) {
        //1
        String str = "Hello World";
        String st = "dlroW olleH";
        isSubstr(str, st);
        //2
        isReverse(str, st);
        //3
        StringBuilder task3 = new StringBuilder("Програмmа на Java");
        System.out.println("Переворот строки \"" + task3 + "\" есть \"" + stringReverse(task3) + "\"");
        //4
        StringBuilder s1 = expressionCreate(3, 56, " + ");
        StringBuilder s2 = expressionCreate(3, 56, " - ");
        StringBuilder s3 = expressionCreate(3, 56, " * ");
        System.out.println(s1);
        System.out.println(s2);
        System.out.println(s3);
        //5
        expressionChange_1(s1, "равно");
        expressionChange_1(s2, "равно");
        expressionChange_1(s3, "равно");
    }
    private static void isSubstr(String str, String st){
        if (str.indexOf(st) != -1)
            System.out.println("Подстрока: \"" + st + "\" + входит в строку: \"" + str + "\".");
        else
            System.out.println("Подстрока: \"" + st + "\" + Не входит в строку: \"" + str + "\".");
    }
    private static void isReverse(String s1, String s2) {
        StringBuilder sb1 = new StringBuilder(s1);
        StringBuilder sb2 = new StringBuilder(s2);
        sb1.reverse();
        if (sb1.compareTo(sb2) == 0)
            System.out.println("Cтроки: \"" + s1 + "\" и \"" + s2 + "\" - являются вращением друг друга.");
        else
            System.out.println("Cтроки: \"" + s1 + "\" и \"" + s2 + "\" - НЕ являются вращением друг друга.");
    }
    private static StringBuilder stringReverse(StringBuilder s1) {

        if (s1.length() == 0)
            return tmp;
        else {
            tmp.append(s1.charAt(s1.length() - 1));
            return stringReverse(s1.deleteCharAt(s1.length() - 1));
        }
    }
    private static StringBuilder expressionCreate(int x, int y, String sign) {
        int result = 0;
        switch (sign) {
            case " + ":
                result = x + y;
                break;
            case " - ":
                result = x - y;
                break;
            case " * ":
                result = x * y;
                break;
        }

        StringBuilder expression = new StringBuilder();
        expression.append(x);
        expression.append(sign);
        expression.append(y);
        expression.append(" = ");
        expression.append(result);
        return expression;

    }
    private static void expressionChange_1(StringBuilder str, String word) {
        str.insert(7, word);
        str.deleteCharAt(12);
        System.out.println(str);
    }           
}
```
