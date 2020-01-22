# Java My MEMO

------------------------------program基本------------------<br>
package 必要パッケージ;

public class クラス名{
    public stat[]ic void main(String[] args){
        フィールド;
        メソッド(必要変数);
    }
    static 戻り値型 メソッド(データ型 変数名,...複数可能){
        メソッド処理;
        return 戻す値の変数;
    }
}

-------------------------------メソッド----------------------<br>
setter--> name プロパティならsetName(String name){this.name = name;}
//ほかclassから書き込み可能
getter-->nameプロパティならgetName(){return this.name;}
//ほかclassから読み込み可能
※プロパティのみだとアクセス修飾子指定で読み書き両方可/不可のみ

-------------------------------Cast------------------------------<br>
String→int　Integer.parseInt(x)
String→double　Double.parseDouble(x)
数値→String　String.valueOf(x)
int →char (char)x;
//String s；
for (char c = s.charAt(0); c <= s.charAt(s.length()-1); c++)
          System.out.println(c);
    } //ｓの最初のアルファベット～ｓの最後のアルファベットを表示
下一桁表示　String.format("%.1f",x)　
　MathClass
小数点以下四捨五入　Math.round(x)
円周率　Math.PI
aのb乗　Math.pow(double a,double b)

------------------------------Scanner(java.util.Scanner) Class-----------------<br>
Scanner sc = new Scanner(System.in)
sc.next() //単語単位
sc.nextLine() //1行単位 読み飛ばしStringが２行目以降の時
sc.nextInt() //数字単語単位
String str[] = sc.nextLine().split("");//一文字づつ配列へ
List<String> line= Arrays.asList(sc.nextLine().split(""));//ラムダ

sc.close()//クローズ

-----------------------------Calendar(java.util.Calendar) Class-----------------------------<br>
Calendar.getInstance() //メソッド...デフォルトのタイムゾーン(基準時刻(グリニッチ天文台)との差/日本は+9時間)とロケール(言語/地域の設定)でカレンダ取得

-------------------------------BigIntegerClass (import java.math.BigInteger)-------------------<br>
和　BigInteger add(BigInteger x)
※BigInteger型はn++は使えないのでn=n.add(BigInteger.ONE) 
        this + x
積　BigInteger multiply(BigInteger x)
        this * x
商　BigInteger divide(BigInteger x)
        this / x
剰余　BigInteger remainder(BIgInteger x)
            this % x
符号判定　int signum()     x.signum() != 1//判定例　整数でない場合
　　　　　x<0 : -1
                    x=0 : 0
                    x>0 : 1
比較　int cimpareTo(BigInteger x)
            this < x : -1
            this = x : 0
            this > x : 1
等価性　boolean equals(Object x)
                this = x
新インスタンス　static BigInteger valueOf(long x)
0　ZERO
1　ONE

------------------------------文字列のメソッド()------------------<br>
文字列の長さ　x.length()
配列の長さ　x.length
xを大文字　x.toUpperCase()
x.charAt(i) //char型 1字
x.substring(i,j) //String型i-1~j字
x.replace(a,b)//　aをbに置換

-----------------------------printf(java.io.Console) メソッドprintf(String format,object...args)-------------<br>
printfで桁指定
最少桁　printf("[%5d]", 123)[△△123]
文字列最大幅　printf([%.3s]", "abcde")[abc]
左詰　printf([%-5s]", "abc")[abc△△]
0詰　printf("[%05d]",123);[00123]
n改行　printf("abc%ndef");abc<改行>def
引数の番号　printf("%3$s,%2$s,%1$s",
"str1","str2","str3");str3,str2,str1
数値の桁数を習得　
int val = 100;int v = String.valueOf(val).length();//3

時間　printf("%tT", new Date());17:04:05
日付　printf("%tF", new Date());2018-01-05
printf("%X", new Date());
X　年＝tY :2018　ty :18
       月＝tm :01
       日＝td :01　te :1
       時＝tH:17　tI:5(L,iどちらも可)
       分＝tM:04
       秒＝tS:05

-----------------------------------比較-------------------------------<br>
==とequals()
s.matches("[0-9]")//正規表現０－９か

importjava.util.regex.Pattern;
String pattrn = "b$" ;
//"~$" 末尾が~//先頭なら"^~"
String str = "abcdefgb" ;
Pattern p = Pattern.compile(pattern);
System.out.println(p.matcher(str).find()) ;       //true

-------------------------------配列-------------------------<br>
for(int[] tmp: array){ 
  for(int val : tmp){ 
  System.out.println(val); } }//2次元配列

int[] data = {4,1,2,5,3}; for(int i=0; i<4; i++){ for(int j=0; j<4-i; j++){ if(data[j]<data[j+1]){ int temp=data[j]; data[j]=data[j+1]; data[j+1]=temp; } } }//配列ソート
  Arrays.sort(i);//ソートメソッド

