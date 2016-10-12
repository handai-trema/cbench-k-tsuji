#Report: cbench
Submission: Oct./12/2016  

##提出者
辻　健太  
33E16012  
長谷川研究室 所属  

##手法
下記の３つの操作を行うことで，  
プロファイルを取得した．  

1. Cbenchの起動およびプロファイリング  
まず，端末１上でcbench-k-tsujiリポジトリにおいて，  
'''
ruby -r profile ./bin/trema run ./lib/cbench.rb > profile_cbench.txt
'''  
によりtremaの実行全体のプロファイルを取りつつ，  
tremaを起動させる．  
このとき，出力結果をprofile_cbench.txtに書き出すように設定した．  

2. ベンチマークテストの実施  
次に，他の端末において，  
'''
./bin/cbench --port 6653 --switches 1 --loops 10 --ms-per-test 10000 --delay 1000 --throughput
'''  
を実行し，ベンチマークテストを実施した．  

3. Cbenchの終了  
最後に，元の端末（端末１）に戻り，  
>control + C  
を入力することでCbenchを終了した．  
そして，同ディレクトリに'profile_cbench.txt'としてプロファイル結果を得た．  
  

##結果と考察
上記のように得た  
[プロファイル結果]（https://raw.githubusercontent.com/handai-trema/cbench-k-tsuji/master/profile_cbench.txt）
より，  
IO.selectにかかる時間[%]が最も長いため，  
IO.selectがボトルネックであると考察する.  


##関連リンク
* [Result of profile] (https://raw.githubusercontent.com/handai-trema/cbench-k-tsuji/master/profile_cbench.txt)
