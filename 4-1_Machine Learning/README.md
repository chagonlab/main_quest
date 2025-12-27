### 데이터 정보
2013년 9월 유럽 신용카드 사용자들의 거래 내역을 포함하고 있습니다.
이 데이터셋은 이틀 간의 거래 내역으로 데이터셋은 크게 불균형하며, 사기 거래(양성 클래스)는 전체 거래의 약 0.17%에 불과합니다.

이 데이터셋은 PCA 변환을 거친 수치형 변수들만 포함하고 있습니다. 안타깝게도 기밀 유지 문제로 인해 원본 특징과 데이터에 대한 자세한 배경 정보는 제공할 수 없습니다.
V1, V2, …, V28은 PCA로 얻은 주성분이며, PCA 변환을 거치지 않은 유일한 특징은 'Time'과 'Amount'입니다.

'Time'은 각 거래와 데이터셋의 첫 거래 사이의 경과 시간(초)을 나타내며, 'Amount'는 거래 금액입니다. 'Amount' 특징은 예시 의존적 비용 민감 학습 등에 사용될 수 있습니다.
'Class'는 응답 변수로, 사기 거래인 경우 1, 그렇지 않은 경우 0의 값을 가집니다.

### 프로젝트 수행
프로젝트에서는 EDA를 통해 이상거래 비율, 거래량에 따른 이상거래 비율, 시간대별 정상거래와 이상거래의 비율을 살펴보았습니다.
그후 Counfusion Metrics, accuracy, precision, recall, roc_auc_score를 계산하는 함수를 만들고, precision_recall_curve 함수를 만들었습니다.

해당 함수를 이용하여 DecisionTreeClassifier, RandomForestClassifier, LogisticRegression, XGBClassifier, VotingClassifier 총 5개의 모델을 테스트하여 XBG를 최종 채택하였습니다.
최종 선정 후에는 최적의 임계값을 찾는 테스트를 하고, 하이퍼파라미터튜닝을 통해 성능을 고도화하였습니다.
