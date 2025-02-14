20240712  title: Reversing-x64Elf-100  level: 1

题目链接：https://adworld.xctf.org.cn/challenges/list?rwNmOdr=1720857654241

附件链接：https://adworld.xctf.org.cn/media/file/task/43ba593623a7434fa5437cdd5c7862a1.re

题解
用ida打开看到的是

```
__int64 __fastcall main(int a1, char **a2, char **a3)
{
  char s[264]; // [rsp+0h] [rbp-110h] BYREF
  unsigned __int64 v5; // [rsp+108h] [rbp-8h]

  v5 = __readfsqword(0x28u);
  printf("Enter the password: ");
  if ( !fgets(s, 255, stdin) )
    return 0LL;
  if ( (unsigned int)sub_4006FD(s) )
  {
    puts("Incorrect password!");
    return 1LL;
  }
  else
  {
    puts("Nice!");
    return 0LL;
  }
}
```

然后分析这个题目是需要让我们输入特定的值使得程序可以走到 **puts("Nice!")** 这个分支里面去，这样我们就需要让(unsigned int)sub_4006FD(s)这个函数的结果不成立，继续往上追溯sub_4006FD函数

```
__int64 __fastcall sub_4006FD(__int64 a1)
{
  int i; // [rsp+14h] [rbp-24h]
  __int64 v3[4]; // [rsp+18h] [rbp-20h]

  v3[0] = (__int64)"Dufhbmf";
  v3[1] = (__int64)"pG`imos";
  v3[2] = (__int64)"ewUglpt";
  for ( i = 0; i <= 11; ++i )
  {
    if ( *(char *)(v3[i % 3] + 2 * (i / 3)) - *(char *)(i + a1) != 1 )
      return 1LL;
  }
  return 0LL;
}
```
可以看到这个函数里面要让返回值为0，才能让我们最终走到我们想要的**puts("Nice!")** 分支上，那在这里的话就需要让输入的s的值能够满足for循环的条件中的*(char *)(v3[i % 3] + 2 * (i / 3)) - *(char *)(i + a1) == 1成立，所以可以编写逆向算法代码

```
key1="Dufhbmf"
key2="pG^imos"
key3="ewUglpt"
flag=""
key4=[key1,key2,key3]
for i in range(12): 
	flag+=chr(ord(key4[i%3][(2*int(i/3))]) -1)
print(flag)
```

最后运行得出flag为

```
Code]Talkers
```





