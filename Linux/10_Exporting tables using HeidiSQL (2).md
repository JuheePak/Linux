### 💾 Exporting tables using HeidiSQL (2)

---

- 이전에 쿼리 결과 or 테이블을 HeidiSQL 을 통해 **Export 하는 방법**을 찾아봤다 
- 1,000건의 결과까지만 저장되는줄 알았는데, 간단하게 설정을 바꾸고 충분히 많은 데이터도 HeidiSQL을 통해 export 할 수 있는 방법을 찾아냈다! (야호 😆) ~~굳이 MySQL Workbench 가 없어도~~
- 저장하는 탭이나 방법은 동일하나 그 전에 설정해주는 부분이 있다
- 마우스 오른쪽 버튼 클릭 **[격자 뷰 옵션] --> [데이터 격자 설정]** 클릭

![11](https://user-images.githubusercontent.com/69948723/107176492-e3477a00-6a12-11eb-9f45-874098a73a14.png)



- 다른건 건들지 말고 페이지 당 최대 행 수 **오른쪽 박스**의 숫자를 크게 바꿔준다

![12](https://user-images.githubusercontent.com/69948723/107176493-e3e01080-6a12-11eb-92a4-3e41f83040de.png)

- 적용 후, 상단의 **[모두 보기]** 버튼을 눌러 모든 행이 조회가 되는지 확인하고, 이전 페이지에서 csv 파일로 export 하는 방법을 다시 해주면 된다

![캡처](https://user-images.githubusercontent.com/69948723/107176495-e478a700-6a12-11eb-8e9c-3be62b31a22e.PNG)

- 데이터 행의 개수가 많을수록 오래 로딩될 수 있다는 점은 주의해야 한다

  