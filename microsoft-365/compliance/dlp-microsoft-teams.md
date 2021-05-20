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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Microsoft Teamsチャットやチャネルに DLP ポリシーを適用できるようになりました。 この記事では、そのしくみについて詳しく説明します。
ms.openlocfilehash: 9fdce86473dcfbb7ec75b9d371b8782d4141ef57
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572467"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>データ損失防止と Microsoft Teams

> [!NOTE]
> 最近、Office 365 E5/A5、Microsoft 365 E5/A5、Microsoft 365情報保護およびガバナンス、またはOffice 365 Advanced Complianceのライセンスを取得したユーザー向けの Microsoft Teamsチャットおよびチャネル メッセージに、データ損失防止機能が追加されました。 Office 365とMicrosoft 365 E3には、オンライン、OneDrive、Exchange Online SharePoint DLP 保護が含まれます。 これには、TeamsがオンラインとOneDriveを SharePoint使用してファイルを共有するため、Teamsを通じて共有されるファイルも含まれます。
Teams チャットでの DLP 保護のサポートには、E5 が必要です。
ライセンス要件の詳細については、「[Microsoft 365 テナントレベル サービスのライセンスに関するガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)」を参照してください。

## <a name="overview-of-dlp-for-microsoft-teams"></a>Microsoft Teams 用 DLP の概要

最近では、**プライベート チャネル メッセージを含む** Microsoft Teamsチャットメッセージやチャネル メッセージを含むように [、データ損失防止](dlp-learn-about-dlp.md)機能が拡張されました。 

> [!IMPORTANT]
> 現在 DLP はチャットまたはチャネル スレッド内の実際のメッセージにのみ適用されます。 アクティビティ通知 (短いメッセージ プレビューを含み、ユーザーの通知設定に基づいて表示される) は、現時点では、Teams DLP には含 **まれていません**。 プレビューに表示されるメッセージの一部に含まれる機密情報は、DLP ポリシーが適用され、メッセージ自体の機密情報が削除された後でも、通知に表示されたままになります。

組織に DLP がある場合、Microsoft Teams チャネルまたはチャット セッションで機密情報を共有できないようにするポリシーを定義できるようになりました。 この保護のしくみの例を次に示します。

- **例 1: メッセージ内の機密情報の保護** あるユーザーが、Teamsチャットまたはチャネルで、ゲスト (外部ユーザー) と機密情報を共有しようとしたとします。 これを防ぐために定義された DLP ポリシーがある場合、外部ユーザーに送信される機密情報を含むメッセージは削除されます。 これは DLP ポリシーの構成方法に従って自動的に数秒以内に行われます。

    > [!NOTE]
    > Microsoft Teams用 DLP は、次のユーザーと共有するMicrosoft Teams機密性の高いコンテンツをブロックします。<br/>- チームとチャンネルでの[ゲストアクセス](/MicrosoftTeams/guest-access)。又は<br/>- 会議やチャット セッションでの[外部アクセス](/MicrosoftTeams/manage-external-access)。 <p>外部チャット セッションの DLP は、送信者と受信者の両方が Teams のみモードで、[ネイティブ フェデレーションを使用している](/microsoftteams/manage-external-access)場合にのみ機能Microsoft Teams。 Teams用 DLP は、Skype for Businessまたはネイティブ以外のフェデレーション チャット セッションと[相互運用](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business)機能を持つメッセージをブロックしません。

- **例 2: 文書内の機密情報を保護する**。 たとえば、Microsoft Teamsチャネルまたはチャットで、ユーザーがドキュメントをゲストと共有しようとして、そのドキュメントに機密情報が含まれているとします。 これを防ぐために定義された DLP ポリシーがある場合、ドキュメントはそれらのユーザーに対して開かれません。 この場合、保護を実施するためには、DLP ポリシーにSharePointとOneDriveを含める必要があります。 (これは、Microsoft Teamsに表示され、ユーザーが Office 365 DLP (Office 365 E3 に含まれる) のライセンスを取得する必要があるが、ユーザーがOffice 365 Advanced Compliance用のライセンスを取得する必要がない SharePoint の DLP の例です。

## <a name="policy-tips-help-educate-users"></a>ポリシーのヒントは、ユーザーを教育するのに役立ちます

dlp が[Exchange、Outlook、web 上でOutlook、](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)[オンラインSharePoint、OneDrive for Business サイト、](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)[およびOfficeデスクトップ クライアント](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)で動作するのと同様に、アクションが DLP ポリシーと競合する場合にポリシーヒントが表示されます。 ポリシーヒントの例を次に示します。

![Teamsでブロックされたメッセージ通知](../media/dlp-teams-blockedmessage-notification.png)

この場合、送信者はMicrosoft Teamsチャネルで社会保障番号を共有しようとしました。 [ **操作方法]** リンクをクリックすると、送信者が問題を解決するためのオプションを提供するダイアログ ボックスが開きます。 この場合、送信者はポリシーを上書きするか、管理者に確認して解決するよう通知することができます。

![ブロックされたメッセージを解決するためのオプション](../media/dlp-teams-blockedmessage-possibleactions.png)

組織では、DLP ポリシーをユーザーが上書きすることを許可できます。 また、DLP ポリシーを構成する際に、既定のポリシー ヒントを使用したり、組織の [ポリシー ヒントをカスタマイズ](#to-customize-policy-tips) したりできます。

送信者がTeamsチャネルで社会保障番号を共有している例に戻ると、受信者が見たものは次のとおりです。

> [!div class="mx-imgBorder"]
> ![メッセージがブロックされました](../media/dlp-teams-blockedmessage-notification-to-user.png)

### <a name="to-customize-policy-tips"></a>ポリシーのヒントをカスタマイズするには

このタスクを実行するには、DLP ポリシーを編集する権限を持つロールを割り当てる必要があります。 詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。

1. セキュリティ& コンプライアンス センター ( [https://protection.office.com](https://protection.office.com) ) に移動してサインインします。

2. [**データ損失防止**  >  **ポリシー ]** を選択します。

3. ポリシーを選択し、[ **ポリシーの設定]** の横にある [ **編集**] を選択します。

4. 新しいルールを作成するか、ポリシーの既存のルールを編集します。

    > [!div class="mx-imgBorder"]
    > ![ポリシーのルールの編集](../media/dlp-teams-editrule.png)

5. [ **ユーザー通知** ] タブ **で、[電子メール テキストのカスタマイズ** ] または [ポリシー ヒント テキスト **のカスタマイズ]** オプションを選択します。

    > [!div class="mx-imgBorder"]
    > ![ユーザー通知とポリシーのヒントをカスタマイズする](../media/dlp-teams-editrule-usernotifications.png)<br/>  

6. 電子メール通知やポリシーのヒントに使用するテキストを指定し、[ **保存**] を選択します。

7. [ **ポリシーの設定]** タブで、[ **保存**] を選択します。

データ センターを通じて変更が動作し、ユーザー アカウントに同期するまで約 1 時間かかります。
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>Microsoft Teams を場所として既存の DLP ポリシーに追加する

このタスクを実行するには、DLP ポリシーを編集する権限を持つロールを割り当てる必要があります。 詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。

1. セキュリティ& コンプライアンス センター ( [https://protection.office.com](https://protection.office.com) ) に移動してサインインします。

2. [**データ損失防止**  >  **ポリシー ]** を選択します。

3. ポリシーを選択し、[場所] の値 **を** 確認します。 **チャットやチャンネルのメッセージTeams** 表示されている場合は、すべて設定されています。 表示しない場合は、[ **編集**] をクリックします。

    > [!div class="mx-imgBorder"]
    > ![既存のポリシーの場所](../media/dlp-teams-editexistingpolicy.png)

4. [**状態]** 列で、**チャットメッセージとチャネル メッセージの** ポリシー Teams有効にします。

    > [!div class="mx-imgBorder"]
    > ![Teamsチャットおよびチャネルの DLP](../media/dlp-teams-addteamschatschannels.png)

5. [ **場所の選択** ] タブで、すべてのアカウントの既定の設定をそのまま使用するか、[特定の **場所を選択できるようにする**] を選択します。 次の情報を指定できます。

    1. 含めるまたは除外する最大1000の個人アカウント
    1. 含めるまたは除外する配布リストとセキュリティ グループ。 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. **[次へ]** を選択します。

7. **[保存]** をクリックします。

データ センターを通じて変更が動作し、ユーザー アカウントに同期するまで約 1 時間かかります。
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Microsoft Teams の新しい DLP ポリシーを定義する

このタスクを実行するには、DLP ポリシーを編集する権限を持つロールを割り当てる必要があります。 詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。

1. セキュリティ& コンプライアンス センター ( [https://protection.office.com](https://protection.office.com) ) に移動してサインインします。

2. [**データ損失防止**  >  **ポリシー**  >  **+ ポリシーの作成**] を選択します。

3. [テンプレート](data-loss-prevention-policies.md#dlp-policy-templates)を選択し、[**次へ**] をクリックします。

    この例では、米国個人を特定できる情報データ テンプレートを選択しました。

    > [!div class="mx-imgBorder"]
    > ![DLP ポリシーのプライバシー テンプレート](../media/dlp-teams-createnewpolicy-template.png)<br/>

4. [ **ポリシー名]** タブで、ポリシーの名前と説明を指定し、[ **次へ**] を選択します。

5. [ **場所の選択** ] タブで、すべてのアカウントの既定の設定をそのまま使用するか、[特定の **場所を選択できるようにする**] を選択します。 次の情報を指定できます。

    1. 含めるまたは除外する最大1000の個人アカウント
    1. 含めるまたは除外する配布リストとセキュリティ グループ。 **これはパブリック プレビュー機能です。**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![DLP ポリシーの場所](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > 機密情報を含むドキュメントがTeamsで不適切に共有されないようにするには、SharePoint **サイト** と **OneDriveアカウント** がオンになっていることを確認 **し、チャットやチャンネルのメッセージTeams。**

6. [ **ポリシーの設定** ] タブ **の [保護するコンテンツの種類をカスタマイズ** する] で、既定の単純な設定をそのまま使用するか、[ **詳細設定を使用** する] をクリックして、[ **次へ**] を選択します。 詳細設定を選択した場合は、ポリシーのルールを作成または編集できます。 (この方法のヘルプを参照するには、「 [簡単な設定と詳細設定」を](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)参照してください)。

7.  [ **ポリシー設定** ] タブの [ **機密情報を検出した場合の対処方法を** 確認しますか? (ここでは、既定の [ポリシー ヒントと電子メール通知](use-notifications-and-policy-tips.md)を保持するか、カスタマイズするかを選択できます。

    > [!div class="mx-imgBorder"]
    > ![ヒントと通知を含む DLP ポリシー設定](../media/dlp-teams-policysettings-tipsemails.png)

    設定の確認または編集が終了したら、[ **次へ**] を選択します。

8. [ **ポリシー設定** ] タブの [ **ポリシーを有効にするか、最初にテストしますか?**] で、ポリシーを有効にするか、テストするか、 [今](dlp-overview-plan-for-dlp.md#policy-deployment)すぐオフにするかを選択し、[ **次へ**] を選択します。

    > [!div class="mx-imgBorder"]
    > ![ポリシーを有効にするかどうかを指定する](../media/dlp-teams-policysettings-turnonnow.png)

9. [ **設定の確認** ] タブで、新しいポリシーの設定を確認します。 **[編集] を** 選択して変更します。 完了したら、[ **作成**] を選択します。

新しいポリシーがデータセンターを通じて動作し、ユーザーアカウントに同期するまで約1時間かかります。

## <a name="prevent-external-access-to-sensitive-documents"></a>機密文書への外部アクセスを防止する

機密情報を含むSharePointドキュメントに、デフォルトでSharePointまたはTeamsから外部ゲストからアクセスできないようにするには、次のオプションを選択します。

- [新しいファイルを既定で機密としてマーク](/sharepoint/sensitive-by-default)することで、DLP がスキャンして共有しても安全であるとマークするまで、ドキュメントが保護されるようにすることができます。

- 推奨される DLP ポリシー構造

    - **条件**
        - コンテンツには、次の機密情報の種類のいずれかが含まれています: [適用するすべてを選択]
        
        - コンテンツが組織外のユーザーとMicrosoft 365共有される
        
          > [!div class="mx-imgBorder"]
          > ![機密性の高いコンテンツの外部共有を検出するための DLP 条件](../media/dlp-teams-external-sharing/external-condition.png)

    - **Actions**
        - 外部ユーザーのコンテンツへのアクセスを制限する
        
        - メールおよびポリシー ヒントでユーザーに通知する
        
        - インシデント レポートを管理者に送信する
        
        > [!div class="mx-imgBorder"]
        > ![機密性の高いコンテンツの外部共有をブロックする DLP アクション](../media/dlp-teams-external-sharing/external-action.png)

外部ゲストと機密情報を含むドキュメントをSharePointで共有しようとすると、DLP ポリシーが動作します。

> [!div class="mx-imgBorder"]
> ![外部共有がブロックされました](../media/dlp-teams-external-sharing/external-sharing-blocked.png)


ゲストが外部ブロックでドキュメントを開こうとしたときに DLP ポリシーが動作Teams:

> [!div class="mx-imgBorder"]
> ![外部アクセスがブロックされました](../media/dlp-teams-external-sharing/external-access-blocked.png)

## <a name="related-articles"></a>関連記事

[DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)

[メール通知を送信して、DLP ポリシーのヒントを表示する](use-notifications-and-policy-tips.md)
