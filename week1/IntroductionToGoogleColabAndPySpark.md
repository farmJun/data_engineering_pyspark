- ## 5. Jupyter Notebook Basics
    - 1. Code cells
        <img width="383" alt="스크린샷 2024-07-07 오후 11 42 01" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/8d68b2ad-02e1-405d-b43c-a6a8426910c6">

        간단한 파이썬의 곱셉 연산이다.
        
        파이썬에서 사칙연산은 외에도 덧셈은 ‘+’, 뺄셈은 ‘-’, 곱셉은 ’*’ 나눗셈은 ‘/’로 사용 가능하다.
        
        ---
        <img width="655" alt="스크린샷 2024-07-07 오후 11 43 08" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/55624171-ef70-4dbc-a1ed-b4d054e6360c">
        
        파이썬의 collections 모듈의 Counter 클래스를 import하는 코드이다.
        
        파이썬만 설치되어 있으면, 별도의 패키지 설치 없이 Counter 클래스를 import하여 사용할 수 있다.
        
        이 Counter 클래스는 데이터의 개수를 측정할 때 아주 유용하다.
        <img width="643" alt="스크린샷 2024-07-07 오후 11 43 21" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/0f942517-810c-479a-a06e-c9a2e6082503">
        
        Counter 생성자는 여러 형태의 데이터를 인자로 받는다. 중복된 데이터가 저장된 배열을 인자로 넘기면, 각 원소가 배열에 몇 번 포함되어있는지 저장된 Counter 객체를 얻을 수 있다.
        
        위는 Counter 생성자에 준영 2번, 지우 1번, 수지 1번이 포함되어 있어서 결과로 위와 같은 Counter 객체를 얻는다. 
        
        ---
        <img width="629" alt="스크린샷 2024-07-07 오후 11 43 36" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/b9d0c6de-d8e8-46e3-bc8a-9b11cd31c485">
        
        파이썬의 출력문이다. print()의 인자로 큰 따옴표, 작은 따옴표 아무거나 사용가능하다.
        
    - 2. Text cells
        <img width="647" alt="스크린샷 2024-07-07 오후 11 43 56" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/bc02b575-183e-42af-9ec5-9db9000a6a3c">
        
        텍스트 셀을 수정하려면, 특정  셀로 이동하여 ENTER 키를 누르거나 마우스로 더블 클릭한다.
        
        그러면 위와 같이 텍스트 셀에 텍스트를 추가할 수 있고, 오른쪽에서 미리 볼 수 있다.
        
        수정 사항 저장은 ESC 키를 누르거나, 다른 셀을 클릭하면 된다.
        
    - 3. Access to the shell
        <img width="653" alt="스크린샷 2024-07-07 오후 11 44 22" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/158a268a-13ba-455a-9e7f-384803cd80a5">
        
        ls는 list의 약자로, 현재 directory에 존재하는 파일들을 리스트로 출력한다.
        
        ---
        <img width="657" alt="스크린샷 2024-07-07 오후 11 44 56" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/5d05882b-493c-4713-8810-7147ff49778e">
        
        pwd는 print working directory의 약자로. 현재 작업 중인 directory 이름을 출력한다.
        
        위에 예시는 현재 작업 중인 directory는 /content이고, 이 directory에 sample_data를 포함한 총 5개의 파일이 존재한다는 뜻이다.
        
    - 4. Installing Spark
        - !apt-get install openjdk-8-jdk-headless -qq > /dev/null
            - OpenJDK 8의 headless 버전을 설치
            - headless 버전은 GUI 관련 라이브러리 없이 Java 설치
            - -qq : 설치 과정에서 출력되는 메시지를 최소화
            - > dev/null : 출력되는 메시지가 화면에 표시되지 않도록 버림.
        - !wget -q http://archive.apache.org/dist/spark/spark-3.5.1/spark-3.5.1-bin-hadoop3.tgz
            - Apache Spark 3.5.1의 바이너리 파일을 다운로드
            - wget : 지정된 URL에서 파일을 다운로드
            - -q : 다운로드 진행 상황을 출력하지 않음.
        - tar xf spark-3.5.1-bin-hadoop3.tgz
            - 다운로드한 tar.gz 파일을 압축 해제
            - tar sf : tar 파일을 추출, x는 extract, f는 file을 의미
        - !pip install -q findspark
            - 파이썬 패키지 findspark를 설치하는 명령어
            - pip install : 지정된 파이썬 패키지를 설치
            - -q : 다운로드 진행 상황을 출력하지 않음.
            - findspark : 파이썬과 Spark 사이의 통합을 쉽게 해주는 패키지
        <img width="636" alt="스크린샷 2024-07-07 오후 11 45 38" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/e1d39739-682b-42dc-9886-a560a04c17e9">
        
        기존 노트북에서 실행하면, 이미 파일이 존재한다고 나와서 복제 후 새 노트북에서 재실행 
        <img width="661" alt="스크린샷 2024-07-07 오후 11 46 33" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/4496a426-dcea-4735-a623-1d541c2f4902">

        대략 13분 정도 소요됨. 
        
        ---
        
        환경 변수 설정
        
        <img width="661" alt="스크린샷 2024-07-07 오후 11 45 54" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/4e75da9c-17a1-4836-b679-a02b01a1af23">
        
        - import os
            - 파이썬의 os 모듈을 import함.
            - os 모듈은 운영 체제와 상호작용하는 기능을 제공하는 표준 라이브러리이다.
            - 이 모듈을 통해 환경 변수 설정, 파일 시스템 경로를 다룰 수 있다.
        - os.environ["JAVA_HOME"] = "/usr/lib/jvm/java-8-openjdk-amd64”
            - JAVA_HOME이란 환경 변수 설정
            - Java의 설치 경로를 os.envirion을 사용해 환경 변수로 설치하여 Spark가 Java의 설치 경로를 알 수 있다.
        - os.environ["SPARK_HOME"] = "/content/spark-3.5.1-bin-hadoop3”
            - SPARK_HOME이란 환경 변수 설정
            - Spark와 관련된 라이브러리 및 실행 파일들의 위치를 알 수 있다.
            <img width="628" alt="스크린샷 2024-07-07 오후 11 46 55" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/20dd084f-ca33-4153-9c50-29b75b8e67e3">
            
        - import findspark
            - findspark 모듈을 import
            - findspark를 통해 spark의 설치 경로를 찾고 설정할 수 있다.
        - findspark.init()
            - findspark를 초기화하낟.
            - Spark의 설치 경로를 환경 변수에서 읽어들여, 파이썬에서 Spark를 사용할 수 있도록 설정.
            - 위에서 설정한 SPARK_HOME 환경 변수로 Spark 라이브러리를 찾음.
        - from pyspark.sql import SparkSession
            - prspark.sql 모듈의 SparkSession을 import
            - pyspark는 파이썬에서 Apache Spark를 사용할 수 있게하는 라이브러리
            - SparkSession은 Spark의 기본 진입점, Spark SQL을 사용하여 데이터 프레임을 생성하고 작업 수행 가능
        - spark = SparkSession.builder.master("local[*]").getOrCreate()
            - Spark Session을 생성
            - SparkSession.builder : Spark Session을 구성하는 빌더 객체 생성
            - .master(”local[*]”) : Spark를 로컬 모드로 실행하며, 모든 CPU 코어를 사용하도록 설정
            - “local[*]” : 시스템의 모든 코어를 사용한다는 뜻.
            - .getOrCreate() : 기존의 Spark Session이 존재하면 그것을 반환하고, 없다면 새로 생성
        - spark.conf.set("spark.sql.repl.eagerEval.enabled", True)
            - Spark Session의 설정을 변경
            - spark.conf.set() : Spark의 설정을 변경하는 메서드
            - “spark.sql.repl.eagerEval.enabled”, True : Spark 데이터 프레임을 출력할 때, 테이블 형식으로 출력되도록  설정.
        - spark
            - SparkSession 객체를 반환 및 출력
  ---
- ## 6. Exploring the Dataset
    - 1. Loading the Dataset
        <img width="655" alt="스크린샷 2024-07-08 오후 6 10 13" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/12ef7f1b-37da-4078-b326-2c5776dbd226">
        
        - !wget https://jacobceles.github.io/knowledge_repo/colab_and_pyspark/cars.csv
        - wget : 지정된 URL에서 파일을 다운로드
        - https://jacobceles.github.io/knowledge_repo/colab_and_pyspark/cars.csv URL에서 cars.csv 파일을 다운로드
        - 다운로드가 성공되면, cars.csv 파일이 현재 작업 디렉토리에 추가됨
            <img width="627" alt="스크린샷 2024-07-08 오후 6 10 27" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/3ad16cb1-ea18-482e-b973-d36aa3113893">
            
            ls 명령어를 통해 확인 가능
            
        - 구글 코랩 말고 로컬에서도 다운로드 받아 csv 파일을 확인
            <img width="482" alt="스크린샷 2024-07-08 오후 6 10 45" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/aedde48f-711c-4031-acf2-fccedd582c13">
            
            ---
            <img width="620" alt="스크린샷 2024-07-08 오후 6 11 02" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/699af61e-8ad8-48a6-be4c-3dcd2cf89bd0">
            
        - df = spark.read.csv('cars.csv', header=True, sep=";")
            - spark.read.csv : Spark의 read 객체를 통해 csv 파일을 읽음
            - ‘cars.csv’ : 읽을 csv 파일의 경로
            - header=True : csv 파일의 첫 번째 row를 헤더로 설정. 출력된 열 이름들이 곧 csv 파일의 첫 번째 행이다
            - sep=”;” : csv 파일에서 열이 ;(세미콜론)으로 구분되어 있음.
        - df.show(5)
            - 데이터 프레임의 처음 5행을 출력한다.
        - header=False로 한 경우
            <img width="625" alt="스크린샷 2024-07-08 오후 6 11 20" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/60eea39a-8c06-40ce-907f-803c6613360f">

            
            - 컬럼명이 c0….cn으로 변경되었고, csv 파일의 첫 번째 행도 데이터 프레임의 행으로 포함된 것을 확인
    - 2. Viewing the Dataframe
        - pyspark에서 dataframe을 조회하는 법
            - df.take(5) : 데이터 프레임의 상위 5개 행을 리스트 형태로 반환.
                <img width="596" alt="스크린샷 2024-07-08 오후 6 12 30" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/78fe762c-209c-46fe-9dac-378bc1bc3308">
                
                ---
                
            - df.collect() : 데이터 프레임의 모든 데이터를 리스트 형태로 반환.
                <img width="611" alt="스크린샷 2024-07-08 오후 6 12 51" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/202df672-24fa-45bf-95fa-22107d8e1237">
                
                ---
                
            - df.show() : 데이터 프레임을 표 형식으로 출력
            - 출력할 행의 수와 데이터의 truncate 여부를 설정 가능
                <img width="600" alt="스크린샷 2024-07-08 오후 6 13 11" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/8577d83d-e1d2-410d-a05e-e87c6ad7a31b">

                
            - df.show(5, truncate=False) : 상위 5개의 행을 잘림 없이 출력
                <img width="605" alt="스크린샷 2024-07-08 오후 6 13 23" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/a78454ac-d222-4543-9144-a12b59877d9f">

                
            - df.show(5, truncate=True) : 상위 5개 행을 출력. 문자열이 긴 경우 … 으로 생략됨
            - 위 사진의 첫 번째 행에서 확인 가능
            - 
            
            ---
            
            - df.limit(5) : 상위 5개 행을 포함하는 새로운 데이터 프레임을 반환
            - Spark의 분산 특성상 항상 같은 결과를 보장하지 않음
                <img width="591" alt="스크린샷 2024-07-08 오후 6 14 24" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/ef87428e-db55-4e5e-868d-775cf8d0e4a9">

                
    - 3. Viewing Dataframe Columns
        - df.columns : 데이터 프레임의 모든 열 이름을 리스트로 반환
            <img width="401" alt="스크린샷 2024-07-08 오후 6 18 49" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/2b14bb7e-bd4d-4a48-8995-1287f357599f">

        
    - 4. Dataframe Schema
        - df.dtypes : 데이터 프레임의 열 이름과 데이터 타입이 튜플 형태로 반환
            <img width="602" alt="스크린샷 2024-07-08 오후 6 15 41" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/4bf6b381-f146-46eb-9c3c-ed7322a74643">
            
        - 기본적으로 spark.read.csv는 모든 데이터를 문자열로 읽어온다.
        - 따라서 df = spark.read.csv('cars.csv', header=True, sep=";", inferSchema=True)를 통해 데이터 타입을 자동으로 추론할 수 있다.
            <img width="637" alt="스크린샷 2024-07-08 오후 6 15 55" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/1fe81433-633b-4d1e-9621-d58e29848a6e">

        - 위 사진처럼 데이터 타입이 바뀌는 것을 확인할 수 있다.
        
        ---
        
        - df.printSchema() : 데이터 프레임의 열 이름과 데이터 타입이 트리 형태로 출력된다
            <img width="596" alt="스크린샷 2024-07-08 오후 6 16 10" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/057d7aed-b121-4ebc-aec5-104568801d98">

        - 마찬가지로 inferSchema=True를 통해 데이터 타입 추론이 가능하다.
            <img width="608" alt="스크린샷 2024-07-08 오후 6 16 26" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/7d266011-eefa-4785-b895-dc9bd1ddcbf1">
        
        ---
        <img width="637" alt="스크린샷 2024-07-08 오후 6 16 53" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/11574248-416a-4e9c-b16e-60cd1b796e1c">
        
        - from pyspark.sql.types import * : pyspark에서 데이터 프레임의 스키마를 정의할 때 사용되는 pyspark.sqk.types 모듈을 import함
            <img width="635" alt="스크린샷 2024-07-08 오후 6 17 25" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/60b41b77-848d-4c50-8911-74cf9bb24191">

      
        - 이 모듈을 통해 각 열의 데이터 타입을 명시적으로 지정할 수 있다.
        <img width="658" alt="스크린샷 2024-07-08 오후 6 17 37" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/52b2a9d0-bec3-4717-b50e-897edcc5cbfa">

        
        - labels : 각 열의 이름과 데이터 타입을 정의하는 튜플을 포함
        - StructType : 데이터 프레임의 스키마를 정의하기 위한 클래스
        - StructField : 스키마의 각 열을 정의하는 클래스, 첫 번째는 요소는 열의 이름, 두 번째 요소는 데이터 타입을 나타냄.
            - x[0] : 열의 이름(ex, 자동차, 실린더, etc...)
            - x[1] : 데이터 타입(ex, StringType(), IntegerType(), etc…)
        - lables를 반복하면서 StructField 객체를 생성하여 StructType에 추가
        - StructFiled의 세 번째 인자는 각 열이 nullable한지 나타낸다
        - 생성된 schema 객체는 데이터 프레임을 생성할 때 사용 가능
        
        ---
        <img width="622" alt="스크린샷 2024-07-08 오후 6 17 53" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/dde693cb-173c-4b5a-bbe4-2401f2cd8968">

        
        - 생성된 schema 객체를 데이터 프레임의 스키마로 설정하여 데이터 프레임을 생성한다.
        - df.printSchema() : schema 객체로 데이터 프레임이 생성됐음을 확인할 수 있다.
            <img width="621" alt="스크린샷 2024-07-08 오후 6 18 06" src="https://github.com/farmJun/data_engineering_pyspark/assets/101688752/b795efa3-233d-431c-bb0b-7166ab940354">

        - df.show()를 통해서도 마찬가지로 확인 가능하다.
- 7. DataFrame Operations on Columns
    - 1. selecting columns
        
        
        - df.Car : 데이터 프레임의 열 이름이 Car인 Column 객체를 반환한다.
        - print(df.Car) : 데이터 프레임의 열 이름이 Car인 Column 객체를 출력한다.
        - print(”*” * 20) : 문자열 “*”를 20번 반복 출력한다.
        - df.select(df.Car).show(truncate=False) :
            - 데이터 프레임의 열 Car를 선택하고, show()로 출력한다.
            - 이때, truncate 옵션을 설정하여, 데이터의 길이가 길 때 자를지 말지 선택한다.
            - 기본적으로 show()는 최초 20개의 행만을 출력한다.
            
        
        - 이 경우에는 열의 대소문자를 구분한다. 그래서 Car이 아닌 car이 되면
        - 데이터 프레임에 ‘car’이란 속성이 없다는 AttributeError가 발생한다.
        
        ---
        
        🚧 주의 🚧 
        
        - 만약에 열의 이름이 예약어 or 데이터 프레임 속성과 같다면 충돌할 수 있다.
        - 열의 이름은 대소문자를 구분하기 때문에, 사용 전 열 이름이 특정 대소문자로 변경됐는지 확인해야 한다.
        - 이를 위해 대괄호 표기법을 사용하는 것이 좋다.
            
            ---
            
            
        - 이전과 다르게 점 표기법이 아니라, 대괄호 표기법을 사용한다.
        - 이 경우에는 대소문자를 구분하지 않는다.
        - df[’Car’] : 데이터 프레임의 열 이름이 Car인 Column 객체를 반환한다.
        - print(df[’Car’]) : 데이터 프레임의 열 이름이 Car인 Column 객체를 출력한다.
        - df.select(df[’Car’]).show(truncate=False) :
            - 데이터 프레임의 열 Car를 선택하고, show()로 출력한다.
        
        ---
      
        
        - from pyspark.sql.functions import col : pyspark.sql.functions 모듈의 col 메서드를 import한다.
        - col() : col() 메서드는 pyspark에서 대소문자를 구분하지 않고 열 이름을 참조한다.
        - col(’car’) : 열의 이름이 ‘car’인 열을 참조한다.
        - df.select(col(’car’)) : 데이터 프레임에서 car 열을 선택한다.
        - df.select(col(’car’)).show(truncate=True) : 데이터 프레임에서 car 열을 선택한 후 show() 메서드를 통해 출력한다.
        
    - 2. selecting multiple columns
        - 여러개의 열을 선택하는 것이다. 하나의 열을 선택하는 것과의 유일한 차이점은 select()함수에 들어가는 열의 개수이다.
            

            
    - 3. adding new columns
        
     
        
        - from pyspark.sql.functions import lit : pyspark.sql.functions 모듈에서 lit() 메서드를 import함
        - lit() : 데이터 프레임에 상수 값을 추가함.
        - withColumn() : 데이터 프레임에 새로운 열을 추가 or 기존 열을 수정 가능
        - df = df.withColumn('박',lit(1)) : 데이터 프레임에 ‘박’이라는 열을 추가하고, 모든 행을 1로 추가
        
        ---
        
        
        - 여러개의 열을 추가하는 것은 withColumn() 메서드를 추가할 열의 개수만큼 사용하면 된다.
        
        ---
        
        
        - from pyspark.sql.functions import concat : pyspark.sql.functions 모듈에서 concat() 메서드를 import함
        - concat() : 여러 열의 값을 결합한다.
        - df.withColumn('준영', concat(col('준'), lit(' '), col('영'))) : 데이터 프레임의 ‘준영’이라는 열을 추가하고, 값은 concat()을 통해, ‘준’ 열의 데이터 + lit(’ ‘) + ‘영’ 열의 데이터를 결합하여 채운다.
            
            
        - 위 사진은 ‘박준영’ 열을 ‘박’, ‘준’, ‘영’ 열의 데이터를 결합하여 추가한 것.
        
        ---
        
    - 4. renaming columns
        
        
        - withColumnRenamed(’a’ , ‘b’) : 데이터 프레임의 ‘a’ 열의 이름을 ‘b’로 수정한다.
        - ‘박’ 열의 이름을 ‘park’으로, ‘준’ 열의 이름을 ‘jun’으로, ‘영’ 열의 이름을 ‘yeong’으로 수정
            
            ```python
            df = df.withColumnRenamed('박', 'park') \
                   .withColumnRenamed('준', 'jun') \
                   .withColumnRenamed('영', 'yeong')
            ```
            
        
    - 5. group by columns
        
        
        - groupBy(’Origin’) : ‘Origin’ 열을 기준으로 데이터 프레임을 그룹화.
        - 그룹화 : 같은 값을 가진 행을 하나의 그룹으로 묶는 것.
        - count() : 그룹화된 각 그룹의 행 수를 센다.
        - df.groupBy('Origin').count().show(5) : ‘Origin’ 열로 그룹화하여 각 그룹의 개수를 세어 상위 5개의 행만 출력한다.
        
        ---
      
        
        - df.groupBy('Origin', ‘Model’).count().show(5) : ‘Origin’ 열과 ‘Model’ 열로 그룹화하여 각 그룹의 개수를 세어 상위 5개의 행만 출력한다
    - 6. removing columns
        
   
        
        - df.drop(’박준영’) : 데이터 프레임에서 열의 이름이 박준영인 열을 제거
            
            
        - 여러개의 열을 동시에 제거하려면 drop() 메서드를 연쇄 호출하면 된다.
