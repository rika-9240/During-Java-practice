# Java My MEMO

------------------------------program基本------------------<br>
package 必要パッケージ;<br>
import java.math; //java.lang以外はimportで使えるようにする...あるいは<br>
//インスタンス生成時　「パッケージ名.class名 クラス変数名 = new パッケージ名.class名();」でも可<br>
<br>
public class クラス名{<br>
    public stat[]ic void main(String[] args){<br>
        フィールド;<br>
        メソッド(必要変数);<br>
    }<br>
    static 戻り値型 メソッド(データ型 変数名,...複数可能){<br>
        メソッド処理;<br>
        return 戻す値の変数;<br>
    }<br>
}<br>

-------------------------------メソッド----------------------<br>
setter--> name プロパティならsetName(String name){this.name = name;}<br>
//ほかclassから書き込み可能<br>
getter-->nameプロパティならgetName(){return this.name;}<br>
//ほかclassから読み込み可能<br>
※プロパティのみだとアクセス修飾子指定で読み書き両方可/不可のみ<br>

-------------------------------Cast------------------------------<br>
String→int　Integer.parseInt(x)<br>
String→double　Double.parseDouble(x)<br>
数値→String　String.valueOf(x)<br>
int →char (char)x;<br>
//String s；<br>
for (char c = s.charAt(0); c <= s.charAt(s.length()-1); c++)<br>
          System.out.println(c);<br>
    } //ｓの最初のアルファベット～ｓの最後のアルファベットを表示<br>
下一桁表示　String.format("%.1f",x)　<br>

------------------------------Scanner(java.util.Scanner) Class-----------------<br>
Scanner sc = new Scanner(System.in)<br>
sc.next() //単語単位<br>
sc.nextLine() //1行単位 読み飛ばしStringが２行目以降の時<br>
sc.nextInt() //数字単語単位<br>
String str[] = sc.nextLine().split("");//一文字づつ配列へ<br>
List<String> line= Arrays.asList(sc.nextLine().split(""));//ラムダ<br>

sc.close()//クローズ

-----------------------------Calendar(java.util.Calendar) Class-----------------------------<br>
Calendar.getInstance() <br>
//メソッド...デフォルトのタイムゾーン(基準時刻(グリニッチ天文台)との差/日本は+9時間)とロケール(言語/地域の設定)でカレンダ取得

------------------------------MathClass------------------<br>
Math.XXX(x)or(x,y);<br>
adx(x)...絶対値<br>
acos(x)...アークコサイン<br>
asin(x)...アークサイン<br>
atan(x)...アークタンジェント<br>
cos(x)...コサイン<br>
sin(x)...サイン<br>
sqrt(x)...平方根<br>
pow(x,y)...xのy乗<br>
PI...円周率<br>
ceil(x)...小数点以下切り上げ<br>
floor(x)...小数点以下切り捨て<br>
round(x)...小数点以下四捨五入<br>
max(x,y)...大きい方<br>
min(x,y)...小さい方<br>

-------------------------------BigIntegerClass (import java.math.BigInteger)-------------------<br>
和　BigInteger add(BigInteger x)<br>
※BigInteger型はn++は使えないのでn=n.add(BigInteger.ONE)<br> 
        this + x<br>
積　BigInteger multiply(BigInteger x)<br>
        this * x<br>
商　BigInteger divide(BigInteger x)<br>
        this / x<br>
剰余　BigInteger remainder(BIgInteger x)<br>
            this % x<br>
符号判定　int signum()     x.signum() != 1//判定例　整数でない場合<br>
　　　　　x<0 : -1<br>
                    x=0 : 0<br>
                    x>0 : 1<br>
比較　int cimpareTo(BigInteger x)<br>
            this < x : -1<br>
            this = x : 0<br>
            this > x : 1<br>
等価性　boolean equals(Object x)<br>
                this = x<br>
新インスタンス　static BigInteger valueOf(long x)<br>
0　ZERO<br>
1　ONE<br>

------------------------------文字列のメソッド()------------------<br>
文字列の長さ　x.length()<br>
配列の長さ　x.length<br>
xを大文字　x.toUpperCase()<br>
x.charAt(i) //char型 1字<br>
x.substring(i,j) //String型i-1~j字<br>
x.replace(a,b)//　aをbに置換<br>
x.replaceAll("[aiueo]","") //複数の文字を置換...この場合aiueoすべて文字列から無くす<br>

-----------------------------printf(java.io.Console) メソッドprintf(String format,object...args)-------------<br>
printfで桁指定
最少桁　printf("[%5d]", 123)[△△123]<br>
文字列最大幅　printf([%.3s]", "abcde")[abc]<br>
左詰　printf([%-5s]", "abc")[abc△△]<br>
0詰　printf("[%05d]",123);[00123]<br>
n改行　printf("abc%ndef");abc<改行>def<br>
引数の番号　printf("%3$s,%2$s,%1$s",<br>
"str1","str2","str3");str3,str2,str1<br>
数値の桁数を習得　<br>
int val = 100;int v = String.valueOf(val).length();//3<br>
<br>
時間　printf("%tT", new Date());17:04:05<br>
日付　printf("%tF", new Date());2018-01-05<br>
printf("%X", new Date());<br>
X　年＝tY :2018　ty :18<br>
       月＝tm :01<br>
       日＝td :01　te :1<br>
       時＝tH:17　tI:5(L,iどちらも可)<br>
       分＝tM:04<br>
       秒＝tS:05<br>
<br>
-----------------------------------比較-------------------------------<br>
==とequals()<br>
==は関係演算子
s.matches("[0-9]")//正規表現０－９か<br>

importjava.util.regex.Pattern;<br>
String pattrn = "b$";<br>
//"~$" 末尾が~<br>
//先頭なら"^~"<br>
String str = "abcdefgb" ;<br>
Pattern p = Pattern.compile(pattern);<br>
System.out.println(p.matcher(str).find());    //true<br>

-------------------------------配列-------------------------<br>
int[] a = {0,2};<br>
for(int i: a){System.out.println(i);} ...あるいは<br>
Arrays.stream(a).forEach(System.out::println);...あるいは<br>
System.out.println(Arrays.toString(a));<br>
System.out.println(a.toString());...配列変数のハッシュ値<br>

代入、拡張for文ではできないよう<br>
        for(int i=0;i<n;i++){<br>
            for(int j=0;j<m;j++){<br>
                mn[i][j] = sc.nextInt();<br>
            }<br>
        }<br>
for(int[] tmp: array){<br> 
  for(int val : tmp){ <br>
  System.out.println(val); } }//2次元配列...あるいは<br>
System.out.println(Arrays.deepToString(array));<br>
System.out.println(Arrays.toString(array));...クラスとハッシュ値<br>
<br>
int[] data = {4,1,2,5,3}; <br>
for(int i=0; i<4; i++){<br>
for(int j=0; j<4-i; j++){<br>
if(data[j]<data[j+1]){ <br>
int temp=data[j]; data[j]=data[j+1]; data[j+1]=temp; } } }//配列ソート<br>
  Arrays.sort(i);//ソートメソッド<br>
  <br>
----------------------------ArrayList<type>------------<br>
ArrayList<type> array = new ArrayList<>();...type intはInteger<br>
ArrayList<Arraylist<type>> array = new ArrayList<>();...2次は先に宣言<br>
    for文などの中...ArrayList<type> array = new ArrayList<>();<br>

------------------------------Set<ラッパーtype>------------<br>
Set<Integer> number = new TreeSet<>();　　          //TreeSet...自然順序付けで格納<br>
number.add(00); //追加<br>
number.addAll(set,0,1,2,3);<br>
number.contains(x) //xがSetの中にないか
   ※for(i=0;i<n;i++){}(インデックス使用ループ)は使えないので注意<br>whileでやったら最初が空になった？？？
　　　print手段<br>
　拡張for文<br>
　Java８からStream/default/forEach<br>
Set<String> set = new HashSet<>();...<br>                                                    
set.stream().filter(v -> v.length() == 4).collect(Collectors.toSet());<br>
set.stream().map(String::toUpperCase).collect(Collectors.toSet());<br>
set.forEach(System.out::println);<br>
   イテレータ<br>
    Set<String> set = new HashSet<>();<br>
Collections.addAll(set, "hoge", "fuga", "bar");<br>
for (Iterator<String> itr = set.iterator(); itr.hasNext();) {<br>
    System.out.println(itr.next());<br>
}<br>

Iterator<String> itr = set.iterator();<br>
while (itr.hasNext()) {<br>
    System.out.println(itr.next());<br>
}<br>


