# Python 05. 데이터 구조 및 활용 workshop

1. ```python
   def get_dict_avg(dic_score):
       avg=sum(dic_score.values()) / len(dic_score)
       print(avg)
   ```

   dictionary에 있는 values를 모두 더하고 항목 개수로 나누어서 평균 구함.

   

2. ```python
   def count_blood(list_blood):
       dic_blood={'A': 0, 'B': 0, 'O': 0, 'AB': 0}
       for i in list_blood:
           dic_blood[i] =dic_blood[i] + 1
       print(dic_blood)
   ```

​		dic_blood 초기화 하고 해당하는 혈액형 입력 들어올 때마다 해당 key의 value를 1씩 커지게 함.

