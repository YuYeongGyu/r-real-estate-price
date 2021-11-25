# r-real-estate-price

### 1. 주제 

  부동산 관련 기사가 부동산 가격에 어느정도 영향을 미치는지를 분석하기 위해 작성 되었습니다. 먼저 부동산 관련 기사의 헤드라인, 본문, 댓글 등에서 빈번히 등장하는 단어를 얻는다. 얻어진 단어들과 실제 부동산 가격과의 관계를 확인해본다.

### 2. 디렉토리

|       디렉토리 이름        |                 디렉토리 내용                 |
| :------------------------: | :-------------------------------------------: |
|          article           | Crawling한 부동산 기사 data (2006.01~2021.06) |
|  seoul_estate_trade_data   |     기사에서 필요한 data를 얻기 위한 코드     |
| [source](Source Code Info) |    기사와 부동산 데이터를 함께 분석한 코드    |


###  3. To Do List

| 번호 | 내용                                                  | 진행 상황            |
| :--: | ----------------------------------------------------- | -------------------- |
|  1   | 가격 상승과 하락에 연관된 word 추출 | 보충 필요 |
|  2   | 부동산 기사와 가격의 상관관계를 확인 | 보충 필요 |

### 4. Source Code Info

- acticle_same_title.ipynb

  : 각 언론사마다 기사를 쓸 때 어떤 단어를 중요하게 사용하는지 알아보기 위해 아래와 같은 방법을 사용하였다.

1. d2v를 사용해서 기사 title에 사용된 word들의 중요도에 대한 정보를 포함한 결과를 얻기 힘들다고 생각하였다.

2. title에 사용된 word들을 언론사마다 doc으로 하여 tf-idf 값을 구하였다.

3. 구해진 tf-idf 값을 weight로 하여 전체 word들에 w2v하여 얻은 결과에 곱해준다. 이때 tf-idf 값을 normalization하여 각 언론사에서 사용된 word들의 tf-idf 값의 합이 1이 되도록 하였다.

   ###### => norm_tf-idf(i) = tf-idf(i)/sum_of_total_tf-idf (i = word)

4. UMAP(cosin)을 이용해 시각화하여 언론사들의 분포를 확인하고 clustering 해본다.

