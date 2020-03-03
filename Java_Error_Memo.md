Mainjava:3: error: illegal character: '\u3000' //全角スペース有り


エラーの確認ポイント
・eclipseとエディタ＋コマンドプロンプトのコンパイルで比較する...Eclipseのコンソールの問題なのかがわかる
例：eclipseのコンソールではprintf出力がすぐ行われずscanfで入力された後のprintfと一緒にコンソールへ出力される<br>
→解決策：出力データを一時記憶するバッファ機能に貯めたデータを強制で吐き出させるfflushを使う...printfとscanffの間に「fflush(0);」を挿入する
