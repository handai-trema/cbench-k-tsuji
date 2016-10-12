#Report: cbench
Submission: Oct./12/2016  

##提出者
辻　健太  
33E16012  
長谷川研究室 所属  

##回答
下記の結果（上位100命令のみ表示）を得た.  
そして，IO.selectにかかる時間が最も長いため，  
IO.selectがボトルネックである.  

 
' %   cumulative   self              self     total'
 time   seconds   seconds    calls  ms/call  ms/call  name
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
  1.88   667.58      2.55   191250     0.01     0.07  BinData::BasePrimitive#_value
  1.88   670.12      2.54   107321     0.02     0.03  BinData::SanitizedField#name_as_sym
  1.71   672.44      2.32   101462     0.02     0.04  Kernel#clone
  1.71   674.76      2.32   266116     0.01     0.01  Fixnum#==
  1.71   677.07      2.31    74061     0.03     3.32  Array#each
  1.70   679.37      2.30    42201     0.05     0.14  BinData::Struct#define_field_accessors_for
  1.53   681.44      2.07   164020     0.01     0.07  BinData::BasePrimitive#snapshot
  1.39   683.32      1.88   166186     0.01     0.01  BinData::Base#has_parameter?
  1.39   685.20      1.88    60075     0.03     0.39  Pio::OpenFlow10::Match::Wildcards#get
  1.38   687.07      1.87    38833     0.05     0.23  BinData::BasePrimitive#assign
  1.31   688.84      1.77   319138     0.01     0.01  Kernel#respond_to?
  1.22   690.49      1.65    80765     0.02     0.21  BinData::Primitive#method_missing
  1.15   692.04      1.55    15420     0.10     0.16  BinData::BaseArgProcessor#separate_args
  1.14   693.58      1.54    38901     0.04     0.11  BinData::IO::Read#readbytes
  1.12   695.09      1.51   109888     0.01     2.19  Class#new
  1.10   696.58      1.49    68589     0.02     0.05  BinData::Struct#include_obj?
  1.06   698.01      1.43   122968     0.01     0.01  BinData::Base#get_parameter
  0.98   699.34      1.33   101462     0.01     0.02  Kernel#initialize_clone
  0.92   700.58      1.24    57123     0.02     0.32  BinData::Struct#define_field_accessors
  0.92   701.82      1.24    34452     0.04     0.24  BinData::BasePrimitive#do_write
  0.91   703.05      1.23   385332     0.00     0.00  Array#[]
  0.87   704.23      1.18     9611     0.12     0.29  Pio::Mac#initialize
  0.86   705.40      1.17    98262     0.01     0.27  BinData::SanitizedPrototype#instantiate
  0.84   706.54      1.14   390333     0.00     0.00  Kernel#nil?
  0.79   707.61      1.07    34452     0.03     0.04  BinData::IO::Write#write_raw
  0.78   708.67      1.06    37648     0.03     0.17  Kernel#format
  0.75   709.69      1.02    27738     0.04     0.45  Array#collect
  0.72   710.66      0.97    41307     0.02     0.06  BinData::IO::Read#read
  0.67   711.57      0.91    83066     0.01     0.39  BinData::Struct#instantiate_all_objs
  0.67   712.48      0.91    26843     0.03     0.15  BinData::Uint8#read_and_return_value
  0.67   713.39      0.91    19237     0.05     0.51  BinData::Struct#find_obj_for_name
  0.67   714.30      0.91    38862     0.02     3.15  BinData::Struct#do_write
  0.66   715.19      0.89    44196     0.02     2.30  BinData::Struct#do_read
  0.64   716.06      0.87    25220     0.03     0.28  BinData::Uint8#assign
  0.64   716.92      0.86    41307     0.02     0.03  BinData::IO::Read::SeekableStream#read_raw
  0.63   717.77      0.85    15420     0.06     0.72  BinData::Base#extract_args
  0.61   718.60      0.83    79742     0.01     0.07  BinData::SanitizedFields#field_names
  0.61   719.42      0.82    14908     0.06     1.17  BinData::Struct#initialize_shared_instance
  0.61   720.24      0.82    38058     0.02     0.11  BinData::BasePrimitive#respond_to?
  0.58   721.02      0.78    53393     0.01     0.02  BinData::SanitizedFields#[]
  0.58   721.80      0.78    21648     0.04     0.60  BinData::Base#eval_parameter
  0.55   722.55      0.75    53393     0.01     0.33  BinData::SanitizedField#instantiate
  0.55   723.30      0.75    36456     0.02     0.03  BinData::IO::Write#flushbits
  0.52   724.00      0.70    57123     0.01     0.09  BinData::SanitizedFields#any_field_has_parameter?
  0.52   724.70      0.70    19673     0.04     0.83  Array#each_index
  0.51   725.39      0.69    20030     0.03     0.05  BinData::Uint8#value_to_binary_string
  0.49   726.06      0.67    48130     0.01     0.02  Kernel#initialize_dup
  0.49   726.73      0.67    19237     0.03     0.05  BinData::Struct#base_field_name
  0.49   727.40      0.67    34452     0.02     0.09  BinData::IO::Write#writebytes
  0.48   728.05      0.65    22442     0.03     0.47  Pio::Type::MacAddress#get
  0.46   728.67      0.62   176474     0.00     0.00  Hash#has_parameter?
  0.46   729.29      0.62    14555     0.04     0.86  Hash#each
  0.44   729.89      0.60    15420     0.04     6.26  BinData::Base#initialize_with_warning
  0.44   730.49      0.60   177285     0.00     0.00  Hash#[]
  0.43   731.07      0.58    16040     0.04    13.56  BinData::Struct#assign_fields
  0.43   731.65      0.58     7204     0.08     0.30  IPAddr#initialize
  0.41   732.21      0.56   180096     0.00     0.00  BasicObject#==
  0.41   732.77      0.56   165383     0.00     0.00  Fixnum#>
  0.41   733.32      0.55    44869     0.01     0.23  BinData::Array#new_element
  0.41   733.87      0.55    19251     0.03     0.14  Gem::Specification#initialize
  0.41   734.42      0.55    33660     0.02     0.15  BinData::InitialLengthPlugin#elements
  0.40   734.96      0.54   127865     0.00     0.00  BasicObject#singleton_method_added
  0.39   735.49      0.53    42215     0.01     0.03  BinData::SanitizedPrototype#has_parameter?
  0.39   736.02      0.53    12010     0.04     0.10  IPAddr#_to_string
  0.38   736.53      0.51    48953     0.01     0.65  BinData::BasePrimitive#do_read
  0.38   737.04      0.51     8002     0.06     0.07  IPAddr#set
  0.37   737.54      0.50    42215     0.01     0.04  BinData::SanitizedField#has_parameter?
  0.36   738.03      0.49    20789     0.02     0.03  BinData::Base.arg_processor
  0.35   738.51      0.48    12010     0.04     0.12  IPAddr#in_addr
  0.34   738.97      0.46    34452     0.01     0.43  BinData::Array#each
  0.34   739.43      0.46     4246     0.11     0.37  BinData::DSLMixin::DSLParser#to_struct_params
  0.33   739.87      0.44    11808     0.04     0.06  BinData::DSLMixin::DSLParser#option?
  0.33   740.31      0.44     2402     0.18     0.25  Pio::Mac#parse_mac_string
  0.33   740.75      0.44    15420     0.03     6.19  BinData::Base#initialize
  0.32   741.18      0.43    93983     0.00     0.00  Kernel#is_a?
  0.32   741.61      0.43    15411     0.03     0.17  Array#any?
  0.32   742.04      0.43   108640     0.00     0.00  Fixnum#&
  0.31   742.46      0.42     8804     0.05     0.09  Pio::Mac#to_s
  0.30   742.87      0.41    15420     0.03     0.10  BinData::RegisterNamePlugin#initialize_shared_instance
  0.30   743.27      0.40    15420     0.03     0.05  BinData::CheckOrAdjustOffsetPlugin#initialize_shared_instance
  0.29   743.66      0.39    14812     0.03     0.03  BinData::Struct::Snapshot#[]=
  0.29   744.05      0.39     6242     0.06     0.12  Hash#fetch
  0.28   744.43      0.38    24828     0.02     0.41  BinData::InitialLengthPlugin#do_read
  0.28   744.81      0.38    11223     0.03     0.04  BinData::Base#furthest_ancestor
  0.27   745.18      0.37   105277     0.00     0.00  Kernel#initialize_copy
  0.27   745.55      0.37    10809     0.03     0.06  BinData::Uint16be#value_to_binary_string
  0.27   745.92      0.37   112776     0.00     0.00  Symbol#to_sym


##関連リンク
* [lib/cbench.rb] (https://github.com/handai-trema/cbench-k-tsuji/blob/master/lib/cbench.rb)
