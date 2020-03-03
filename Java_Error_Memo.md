Mainjava:3: error: illegal character: '\u3000' //全角スペース有り

java.lang.IllegalAccessError: class testUnitSample.Color1Test (in module testUnitSample) cannot access class org.hamcrest.CoreMatchers (in unnamed module @0x3b2c72c2) because module testUnitSample does not read unnamed module @0x3b2c72c2 //module-info.javaの作成付きのプロジェクトでJunitテストクラスを実行すると出る...module-info.javaを消せば消える・使うときはほかの対処探そう





エラーの確認ポイント
・eclipseとエディタ＋コマンドプロンプトのコンパイルで比較する...Eclipseのコンソールの問題なのかがわかる
例：eclipseのコンソールではprintf出力がすぐ行われずscanfで入力された後のprintfと一緒にコンソールへ出力される<br>
→解決策：出力データを一時記憶するバッファ機能に貯めたデータを強制で吐き出させるfflushを使う...printfとscanffの間に「fflush(0);」を挿入する
