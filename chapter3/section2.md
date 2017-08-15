# Filter运算符

FILTER 运算符用于根据条件从关系中选择所需的元组。

语法

下面给出了 FILTER 运算符的语法。

grunt&gt; Relation2\_name = FILTER Relation1\_name BY \(condition\);

\(1,Rajiv,Reddy,9848022337,Hyderabad\)

\(2,siddarth,Battacharya,9848022338,Kolkata\)

\(3,Rajesh,Khanna,9848022339,Delhi\)

\(4,Preethi,Agarwal,9848022330,Pune\)

\(5,Trupthi,Mohanthy,9848022336,Bhuwaneshwar\)

\(6,Archana,Mishra,9848022335,Chennai.\)

\(7,Komal,Nayak,9848022334,trivendram.\)

\(8,Bharathi,Nambiayar,9848022333,Chennai.\)

grunt&gt; describe student ;

student: {id: int,firstname: chararray,lastname: chararray,phone: chararray,city: chararray}

grunt&gt; filter\_data = filter student by city == 'Chennai.' ; dump filter\_data ;

\(6,Archana,Mishra,9848022335,Chennai.\)

\(8,Bharathi,Nambiayar,9848022333,Chennai.\)





