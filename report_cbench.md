#Report: cbench
Submission: Oct./12/2016  

##提出者
辻　健太  
33E16012  
長谷川研究室 所属  

##回答
下記の結果（上位10命令のみ表示）を得た.  
そして，IO.selectにかかる時間が最も長いため，  
IO.selectがボトルネックである.  

  %   cumulative   self              self     total  
 time   seconds   seconds    calls  ms/call  ms/call  name  
------------------------------------------------------------------
190.42   257.75    257.75        2 128875.00 128875.00  IO.select  
 95.26   386.70    128.95        2 64475.00 64475.00  Thread#join  
 95.21   515.58    128.88        2 64440.00 64440.00  TCPServer#accept  
 95.15   644.37    128.79      149   864.36   864.36  Kernel#sleep  
  3.61   649.25      4.88    82044     0.06     0.08  Kernel#dup  
  2.72   652.93      3.68    87038     0.04     0.27  BinData::Struct#instantiate_obj_at  
  2.40   656.18      3.25   101191     0.03     0.10  BinData::BasePrimitive#method_missing  
  2.24   659.21      3.03   126822     0.02     0.03  Kernel#define_singleton_method  
  2.17   662.15      2.94   223038     0.01     0.05  BasicObject#!=  
  2.13   665.03      2.88    98262     0.03     0.26  BinData::Base#new  


##関連リンク
* [Result of profile] (https://github.com/handai-trema/cbench-k-tsuji/blob/master/profile_cbench.txt)
