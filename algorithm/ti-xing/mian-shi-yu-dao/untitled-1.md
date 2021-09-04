# 数字转Excel列名

刷的太少,写起来很慢. 没时间写完了.

事中33%

事后查:

```text
import java.io.*;
import java.util.*;

class Solution{

    public String getColumn(int num){
        //26 Z , 27 AA , 52 AZ, 53 BA, ??? ABC
        int a = num;
        int b;
        String out = "";
        while(a > 0){
            a = (num-1)/26;
            b = (num -1) %26;
            out = "" + (char)(b + 65) + out;
            num = a;
        }
        return out;
    }

}

public class Main
{
    public static void main(String args[])
    {
        Scanner sc = new Scanner(System.in);
        int out;
        while(sc.hasNextInt()){
            out = sc.nextInt();
            Solution s = new Solution();
            String answer = s.getColumn(out);
            System.out.println(answer);
        }

    }
}
```

