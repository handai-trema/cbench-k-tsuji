#Report: cbench
Submission: Oct./12/2016  
Branch:     Master  


##提出者
辻　健太  
33E16012  
長谷川研究室 所属  



##実施内容
下記の３つの操作を行うことで，  
[プロファイル結果](https://raw.githubusercontent.com/handai-trema/cbench-k-tsuji/master/profile_cbench.txt)
を取得した．  

###① Cbenchの起動およびプロファイリング  
まず，端末１上でcbench-k-tsujiリポジトリにおいて，  
```
ruby -r profile ./bin/trema run ./lib/cbench.rb &> profile_cbench.txt
```  
によりtremaの実行全体のプロファイルを取りつつ，tremaを起動させる．  
このとき，出力結果を`profile_cbench.txt`に書き出すように設定した．  
そして，tremaによる出力はエラー出力扱いであることが判明した．  

###② ベンチマークテストの実施  
次に，他の端末において，  
```
./bin/cbench --port 6653 --switches 1 --loops 10 --ms-per-test 10000 --delay 1000 --throughput
```  
を実行し，ベンチマークテストを実施した．  

###③ Cbenchの終了  
最後に，元の端末（端末１）に戻り，  
```
control + C
```  
を入力することでCbenchを終了した．  
そして，同ディレクトリに
[profile_cbench.txt]
(https://raw.githubusercontent.com/handai-trema/cbench-k-tsuji/master/profile_cbench.txt)
としてプロファイル結果を得た．  


##結果と考察
上記のように得た
[プロファイル結果](https://raw.githubusercontent.com/handai-trema/cbench-k-tsuji/master/profile_cbench.txt)
より，IO.selectにかかる時間[%]が最も長いため，IO.selectがボトルネックであると考察する.  

ちなみに，IO.selectとは下に示すメソッドである．  
<b>入力:</B> 入力/出力/例外待ちのIOオブジェクト  
<b>出力:</B> 準備ができた順番の配列  
<b>使われ方:</B> 主に，TCPコネクションの打ち切りの際  
>参考：  
> * [Ruby 2.3.0 リファレンスマニュアル - IO.select](https://docs.ruby-lang.org/ja/latest/method/IO/s/select.html)
> * [RubyのIO.select を使って、TCP socketで返信がなくなったら自動でコネクションをきる方法](http://portaltan.hatenablog.com/entry/2015/07/28/154113)




##関連リンク
* [プロファイル結果] (https://raw.githubusercontent.com/handai-trema/cbench-k-tsuji/master/profile_cbench.txt)
