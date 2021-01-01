---
description: 2020.01.01
---

# 05 替换空格

![https://leetcode-cn.com/problems/ti-huan-kong-ge-lcof/](../../.gitbook/assets/image%20%283%29.png)

**Noob‘s Solution:**

```text
class Solution {
    public String replaceSpace(String s) {
            String[] words = s.split("");
            StringBuilder out = new StringBuilder();
            for(int a = 0;a < words.length;a++)
            {
                if(!words[a].equals(" "))
                    out.append(words[a]);
                else
                    out.append("%20");
            }
            return out.toString();
    }
}
```

**别人的Solution\(CS\_Note\):**

```text
public String replaceSpace(StringBuffer str) {
    int P1 = str.length() - 1;
    for (int i = 0; i <= P1; i++)
        if (str.charAt(i) == ' ')
            str.append("  ");

    int P2 = str.length() - 1;
    while (P1 >= 0 && P2 > P1) {
        char c = str.charAt(P1--);
        if (c == ' ') {
            str.setCharAt(P2--, '0');
            str.setCharAt(P2--, '2');
            str.setCharAt(P2--, '%');
        } else {
            str.setCharAt(P2--, c);
        }
    }
    return str.toString();
}
```



