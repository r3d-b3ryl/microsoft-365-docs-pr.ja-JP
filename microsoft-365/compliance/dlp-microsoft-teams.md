---
title: データ損失防止と Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Microsoft Teams のチャットとチャネルでは、データ損失防止 (DLP) ポリシーがサポートされています。
ms.openlocfilehash: 5d2ee7cefc23a85aec1a75fbe9fe121feacbb51f
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66638369"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>データ損失防止と Microsoft Teams

組織に Microsoft Purview データ損失防止 (DLP) がある場合は、Microsoft Teams チャネルまたはチャット セッションでユーザーが機密情報を共有できないようにするポリシーを定義できます。 この保護のしくみの例を次に示します。

- **例 1: メッセージ内の機密情報を保護する**。 ユーザーが Teams チャットまたはチャネルで機密情報をゲスト (外部ユーザー) と共有しようとするとします。 これを防ぐために DLP ポリシーが定義されている場合、外部ユーザーに送信される機密情報を含むメッセージは削除されます。 これは、DLP ポリシーの構成方法に従って、自動的に数秒以内に発生します。

    > [!NOTE]
    > 以下を持つ Microsoft Teams ユーザーと共有すると、Microsoft Teams の DLP によって機密コンテンツがブロックされます。<br/>- チームとチャネルでの[ゲスト アクセス](/MicrosoftTeams/guest-access)。または<br/>- 会議やチャット セッションの[外部アクセス](/MicrosoftTeams/manage-external-access)。 <p>外部チャット セッションの DLP は、送信者と受信者の両方が Teams のみモードで [、Microsoft Teams ネイティブ フェデレーション](/microsoftteams/manage-external-access)を使用している場合にのみ機能します。 TEAMS の DLP では、Skype for Businessまたは非ネイティブフェデレーション チャット セッションとの[相互運用](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business)中のメッセージはブロックされません。

- **例 2: ドキュメント内の機密情報を保護する**。 ユーザーが Microsoft Teams チャネルまたはチャットのゲストとドキュメントを共有しようとして、ドキュメントに機密情報が含まれているとします。 これを防ぐために DLP ポリシーが定義されている場合、ドキュメントはそれらのユーザーには開きません。 保護を適用するには、DLP ポリシーに SharePoint と OneDrive を含める必要があります。 これは、Microsoft Teams に表示される SharePoint の DLP の例です。そのため、ユーザーは Office 365 DLP (Office 365 E3に含まれます) のライセンスを取得する必要がありますが、ユーザーにOffice 365 Advanced Complianceのライセンスを付与する必要はありません)。

- **例 3: Teams 共有チャネルでの通信の保護**。 共有チャネルの場合、ホスト Teams チーム DLP ポリシーが適用されます。 たとえば、Contoso の TeamA が所有する共有チャネルがあるとします。 TeamA には DLP ポリシー P1 があります。 チャネルを共有するには、次の 3 つの方法があります。
    - **メンバーと共有** する: ユーザー 1 を TeamA のメンバーにすることなく、Contoso から共有チャネルに参加するよう招待します。 この共有チャネル内のすべてのユーザー (user1 を含む) は、P1 によってカバーされます。
    - **チームと共有する (内部的):** Contoso の別のチーム TeamB とチャネルを共有します。 別のチームが異なる DLP ポリシーを持っている可能性がありますが、それは重要ではありません。 P1 は、TeamA ユーザーと TeamB ユーザーの両方を含め、この共有チャネルのすべてのユーザーに適用されます。
    - **チームと共有する (テナント間):** Fabrikam のチーム TeamF とチャネルを共有します。 Fabrikam には独自の DLP ポリシーがある場合がありますが、それは問題ではありません。 P1 は、TeamA (Contoso) ユーザーと TeamF (Fabrikam) ユーザーの両方を含め、この共有チャネルのすべてのユーザーに適用されます。
 
## <a name="dlp-licensing-for-microsoft-teams"></a>Microsoft Teams の DLP ライセンス

[データ損失防止](dlp-learn-about-dlp.md) 機能には、Microsoft Teams チャットとチャネル メッセージが含まれます。これには、次の **プライベート チャネル メッセージが含まれます** 。

- Office 365 E5/A5/G5
- Microsoft 365 E5/A5/G5
- Microsoft 365 E5/A5/G5 Information Protection とガバナンス
- Microsoft 365 E5/A5/G5/F5 Compliance and F5 Security & Compliance

Office 365とMicrosoft 365 E3には、SharePoint Online、OneDrive、およびExchange Onlineの DLP 保護が含まれます。 これには、Teams が SharePoint Online と OneDrive を使用してファイルを共有するため、Teams を介して共有されるファイルも含まれます。

Teams Chat での DLP 保護のサポートには、E5 が必要です。

ライセンス要件の詳細については、「[Microsoft 365 テナントレベル サービスのライセンスに関するガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)」を参照してください。

> [!IMPORTANT]
> DLP は、チャットまたはチャネル スレッド内の実際のメッセージにのみ適用されます。 アクティビティ通知は、短いメッセージ プレビューを含み、ユーザーの通知設定に基づいて表示されます。Teams DLP **には含まれません** 。 プレビューに表示されるメッセージの一部に存在するすべての機密情報は、DLP ポリシーが適用され、メッセージ自体の機密情報が削除された後でも、通知に表示されたままになります。

## <a name="scope-of-dlp-protection"></a>DLP 保護の範囲

DLP 保護は Teams エンティティに異なる方法で適用されます。

|ポリシーのスコープが設定されている場合 |これらの Teams エンティティ |DLP 保護が使用可能になります|
|---------|---------|---------|
|個々のユーザー アカウント     |1:1/n チャット         |はい         |
|     |標準チャネル メッセージと共有チャネル メッセージ         |いいえ         |
|     |Teams のチャネル メッセージ         |はい         |
|セキュリティ グループ/配布リスト  | 1:1/n チャット         |はい         |
|     |標準チャネル メッセージと共有チャネル メッセージ  |いいえ         |
|     |Teams のチャネル メッセージ         |はい        |
|Microsoft 365 グループ    |1:1/n チャット          |不要         |
|     |標準チャネル メッセージと共有チャネル メッセージ          |はい        |
|     |Teams のチャネル メッセージ|不要| 


## <a name="policy-tips-help-educate-users"></a>ポリシーのヒントは、ユーザーの教育に役立ちます

[Exchange、Outlook、Outlook on the web、](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)[SharePoint Online、OneDrive for Business サイト、](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)[および Office デスクトップ クライアント](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)での DLP の動作と同様に、アクションが DLP ポリシーでトリガーされたときにポリシーのヒントが表示されます。 ポリシー ヒントの例を次に示します。

![Teams でブロックされたメッセージ通知。](../media/dlp-teams-blockedmessage-notification.png)

ここでは、送信者が Microsoft Teams チャネルで社会保障番号を共有しようとしました。 [ **どうすればよいですか?** ] リンクをクリックすると、送信者が問題を解決するためのオプションを提供するダイアログ ボックスが開きます。 送信者はポリシーをオーバーライドするか、管理者に確認と解決を通知することができます。

![ブロックされたメッセージを解決するためのオプション。](../media/dlp-teams-blockedmessage-possibleactions.png)

組織では、ユーザーが DLP ポリシーをオーバーライドすることを許可することを選択できます。 DLP ポリシーを構成するときに、既定のポリシー ヒントを使用するか、組織の [ポリシー ヒントをカスタマイズ](#to-customize-policy-tips) できます。

送信者が Teams チャネルで社会保障番号を共有した例に戻り、受信者が見た内容を次に示します。

> [!div class="mx-imgBorder"]
> ![ブロックされたメッセージ。](../media/dlp-teams-blockedmessage-notification-to-user.png)

### <a name="to-customize-policy-tips"></a>ポリシーのヒントをカスタマイズするには

このタスクを実行するには、DLP ポリシーを編集する権限を持つロールを割り当てる必要があります。 詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。

1. Purview コンプライアンス センター ([https://compliance.microsoft.com](https://compliance.microsoft.com)) に移動し、サインインします。

2. **[データ損失防止]** > **[ポリシー]** の順に選択します。

3. ポリシーを選択し、[ **ポリシー設定**] の横にある **[編集]** を選択します。

4. 新しいルールを作成するか、ポリシーの既存のルールを編集します。

5. [ **ユーザー通知** ] タブで、[ **電子メール テキストのカスタマイズ** ] または [ **ポリシー ヒント テキスト オプションのカスタマイズ** ] の順に選択します。

6. 電子メール通知やポリシーヒントに使用するテキストを指定し、[ **保存]** を選択します。

7. [ **ポリシー設定** ] タブで、[ **保存**] を選択します。

変更がデータ センターを経由して動作し、ユーザー アカウントに同期されるようにするには、約 1 時間かかります。
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>Microsoft Teams を場所として既存の DLP ポリシーに追加する

このタスクを実行するには、DLP ポリシーを編集する権限を持つロールを割り当てる必要があります。 詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。

1. コンプライアンス センター ([https://compliance.microsoft.com](https://compliance.microsoft.com)) に移動し、サインインします。

2. **[データ損失防止]** > **[ポリシー]** の順に選択します。

3. ポリシーを選択し、[ **場所]** の下の値を確認します。 **Teams チャットメッセージとチャネル メッセージ** が表示された場合は、すべて設定されています。 そうでない場合は、[ **編集]** をクリックします。

4. [ **状態]** 列で、 **Teams チャットとチャネル メッセージ** のポリシーをオンにします。

5. [ **場所の選択** ] タブで、すべてのアカウントの既定の設定をそのまま使用するか、[ **特定の場所を選択できるようにする] を選択** します。 次の情報を指定できます。

    1. 含めるまたは除外する最大 1,000 個の個々のアカウント
    1. 含めるか除外する配布リストとセキュリティ グループ。 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. **[次へ]** を選択します。

7. [**保存**] をクリックします。

変更がデータ センターを経由して動作し、ユーザー アカウントに同期されるようにするには、約 1 時間かかります。
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Microsoft Teams の新しい DLP ポリシーを定義する

このタスクを実行するには、DLP ポリシーを編集する権限を持つロールを割り当てる必要があります。 詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。

1. コンプライアンス センター ([https://compliance.microsoft.com](https://compliance.microsoft.com)) に移動し、サインインします。

2. **[データ損失防止]** > **[ポリシー]** > **[+ ポリシーの作成]** の順に選択します。

3. [テンプレート](data-loss-prevention-policies.md#dlp-policy-templates)を選択し、[**次へ**] を選択します。

    この例では、米国の個人を特定できる情報データ テンプレートを選択しました。

4. [ **ポリシーの名前]** タブで、ポリシーの名前と説明を指定し、[ **次へ**] を選択します。

5. [ **場所の選択** ] タブで、すべてのアカウントの既定の設定をそのまま使用するか、[ **特定の場所を選択できるようにする] を選択** します。 次の情報を指定できます。

    1. 含めるまたは除外する最大 1,000 個の個々のアカウント
    1. 含めるか除外する配布リストとセキュリティ グループ。 **これはパブリック プレビュー機能です。**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

 
    > [!NOTE]
    > 機密情報を含むドキュメントが Teams で不適切に共有されないようにするには、 **SharePoint サイト** と **OneDrive アカウント** が有効になっていることを確認し、 **Teams チャットやチャネル メッセージ** も有効にします。

6. [ **ポリシー設定** ] タブの [ **保護するコンテンツの種類をカスタマイズする**] で、既定の単純な設定をそのまま使用するか、[ **詳細設定の使用**] を選択して、[ **次へ**] を選択します。 詳細設定を選択した場合は、ポリシーのルールを作成または編集できます。 これに関するヘルプについては、「 [単純な設定と詳細設定](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)」を参照してください。

7.  [ **ポリシー設定** ] タブの [ **機密情報が検出された場合の対処** 方法] で、設定を確認します。 ここでは、既定の [ポリシー ヒントと電子メール通知](use-notifications-and-policy-tips.md)を保持するか、カスタマイズするかを選択できます。



    設定の確認または編集が完了したら、[ **次へ**] を選択します。

8. [**ポリシー設定**] タブの [**ポリシーを有効にするか、最初にテストしますか?**[](dlp-overview-plan-for-dlp.md#policy-deployment)

9. [ **設定の確認** ] タブで、新しいポリシーの設定を確認します。 [ **編集] を** 選択して変更を加えます。 完了したら、[作成] を選択 **します**。

新しいポリシーがデータ センターを経由して動作し、ユーザー アカウントと同期するには、約 1 時間かかります。

## <a name="prevent-external-access-to-sensitive-documents"></a>機密文書への外部アクセスを防止する

機密情報を含む SharePoint ドキュメントに、既定で SharePoint または Teams から外部ゲストがアクセスできないようにするには、次を選択します。

- [既定で新しいファイルを機密性の高](/sharepoint/sensitive-by-default)いファイルとしてマークすることで、DLP がスキャンして安全な共有としてマークされるまで、ドキュメントが確実に保護されるようにすることができます。

- 推奨される DLP ポリシー構造

    - **条件**
        - コンテンツには、次のいずれかの機密情報の種類が含まれています: [適用するすべてを選択]
        
        - コンテンツは、Microsoft 365 から組織外のユーザーと共有されます
        
          > [!div class="mx-imgBorder"]
          > ![機密コンテンツの外部共有を検出するための DLP 条件。](../media/dlp-teams-external-sharing/external-condition.png)

    - **アクション**
        - 外部ユーザーのコンテンツへのアクセスを制限する
        
        - メールおよびポリシー ヒントでユーザーに通知する
        
        - インシデント レポートを管理者に送信する
        
        > [!div class="mx-imgBorder"]
        > ![機密コンテンツの外部共有をブロックする DLP アクション。](../media/dlp-teams-external-sharing/external-action.png)

外部ゲストと機密情報を含むドキュメントを SharePoint で共有しようとすると、DLP ポリシーが動作します。

> [!div class="mx-imgBorder"]
> ![外部共有がブロックされています。](../media/dlp-teams-external-sharing/external-sharing-blocked.png)

<!--DLP policy in action when guest attempts to open a document in Teams with block external:
can't use the below image it contains a non-approved name.
> [!div class="mx-imgBorder"]
> ![External access blocked.](../media/dlp-teams-external-sharing/external-access-blocked.png)-->

## <a name="related-articles"></a>関連記事

- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
- [メール通知を送信して、DLP ポリシーのヒントを表示する](use-notifications-and-policy-tips.md)
