22/10/2023
## Sequence(Postgres)
- Create
    > CREATE SEQUENCE sequence_name  
    [ INCREMENT increment_value ]  
    [ MINVALUE min_value ]   
    [ MAXVALUE max_value ]  
    [ START start_value ]  
    [ CACHE cache_value ];
- Example    
   Create sequence seq_id 
   increment 1   
   minvalue 1  
   start 1  
   Khi để default cho giá trị của 1 field trong table **nextval('seq_name')**  
   + TH1: Khi không gán giá trị cho field đó thì sẽ lấy giá trị tiếp theo của sequence.
   + TH2: Khi gán giá trị cho field đó thì giá trị đó không được gán vào sequence  
    hiện tại nên có thể bị trùng.(có thể sau khi insert rồi gán lại sequence.)

