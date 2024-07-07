- 5. Jupyter Notebook Basics
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
