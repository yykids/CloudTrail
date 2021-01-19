## CloudTrail > コンソール使用ガイド

### 始める
CloudTrailは、組織を有効にするとデフォルトで提供されるサービスです。したがって、組織を作成している場合は別途行う作業はありません。
組織を作成した後、サービス選択でCloudTrailサービスを選択すると使用できます。

![cloudtrail_01](https://static.toastoven.net/prod_cloudtrail/IMG01_JA.png)

### リスト

CloudTrailサービスを選択すると、次のような画面が現れます。

![cloudtrail_02](https://static.toastoven.net/prod_cloudtrail/IMG02_JA.png)

該当組織内でユーザーイベントが記録され、これを確認できます。

### 検索およびソート機能

![cloudtrail_03](https://static.toastoven.net/prod_cloudtrail/IMG03_JA.png)

1. プロジェクトを検索します。名前単位でのみ検索できます。
2. ソース(イベントが発生した場所)単位で検索します。
    - ADMIN_CONSOLE：管理者コンソールで発生したイベント
    - API：システム内部的に発生したイベント 
        - [参考]パッチ作業や予約された作業、アラームなどのイベントが記録されます。
    - USER_CONSOLE：組織内部会員ユーザーコンソールで発生したイベント
3. サービス単位で検索します。 
    - サービスは複数の項目を検索できます。
    - [参考]サービスはTOASTクラウドサービス単位です。
4. イベント単位で検索します。
    - イベントは複数の項目を検索できます。
5. 사용자를 검색합니다.
6. リクエスト、レスポンス値を検索します。
7. 検索範囲を指定します。24時間、1週間、2ヶ月、3ヶ月単位フィルタが提供され、直接指定できます。
    - [参考]イベントは最大3ヶ月間保存されます。
8. リスト表示単位を指定します。1画面に複数のリストを表示するか、20、50、100個単位に設定できます。

---

* ソート機能は時間項目でのみ使用できます。

### 詳細表示機能

![cloudtrail_04](https://static.toastoven.net/prod_cloudtrail/IMG04_JA.png)

行を選択すると該当の行が拡張され、詳細イベントが表示されます。

リクエストとレスポンス結果を表示し、どんなリクエストを送ったかを確認できます。

### 로그 저장/다운로드 설정
해당 조직 내에서 기록된 사용자 이벤트 로그를 외부 Object Storage를 통해 저장/다운로드 할 수 있습니다.
**로그 저장/다운로드 설정** 버튼을 클릭한 후 대화 상자에서 사용 여부를 선택합니다.

![cloudtrail_05](https://static.toastoven.net/prod_cloudtrail/IMG05_JA.png)

* 아래부터는 [TOAST Object Storage](/Storage/Object%20Storage/ko/Overview/)를 이용한 로그 저장/다운로드 방법을 설명합니다.
   * **액세스 키**, **비밀 키**는 [AWS S3 API](/Storage/Object%20Storage/ko/s3-api-guide/#_1)를 이용한 **EC2 자격 증명 등록 및 조회**로 확인할 수 있습니다.
   * **버킷이름**은 로그가 저장될 Object Storage 컨테이너의 이름입니다.
   * **엔드포인트**, **리전**은 로그를 저장할 Object Storage를 관리할 정보이며, [Amazon S3 호환 API 가이드 - AWS SDK](/Storage/Object%20Storage/ko/s3-api-guide#aws-sdk)에서 확인할 수 있습니다.
   * 설정이 완료되면 설정한 Object Storage에 로그가 저장됩니다.
   * 저장된 로그는 2시간~2시간반 후 Object Storage에 업로드된 이후 확인 가능합니다. 
