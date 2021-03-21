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
description: これで、Microsoft Teams のチャットとチャネルに DLP ポリシーを適用できます。 この記事では、その動作について詳しくは、この記事を参照してください。
ms.openlocfilehash: 3a7b228292952bdba3c950b8ab67501c40e99238
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917923"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>データ損失防止と Microsoft Teams

> [!NOTE]
> データ損失防止機能は、Office 365 E5/A5、Microsoft 365 E5/A5、Microsoft 365 Information Protection and Governance、または Office 365 Advanced Compliance のライセンスを取得したユーザー向け Microsoft Teams チャットおよびチャネル メッセージに最近追加されました。 Office 365 および Microsoft 365 E3 には、SharePoint Online、OneDrive、および Exchange Online の DLP 保護が含まれます。 また、Teams は SharePoint Online と OneDrive を使用してファイルを共有するために Teams を介して共有されるファイルも含まれます。
Teams チャットでの DLP 保護のサポートには、E5 が必要です。
ライセンス要件の詳細については、「[Microsoft 365 テナントレベル サービスのライセンスに関するガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)」を参照してください。

## <a name="overview-of-dlp-for-microsoft-teams"></a>Microsoft Teams 用 DLP の概要

最近では [、データ損失防止](data-loss-prevention-policies.md) (DLP) 機能が拡張され、Microsoft Teams のチャット メッセージとチャネル メッセージ (プライベート チャネル メッセージを含む) **が含まれるまで拡張されました**。

組織に DLP がある場合は、Microsoft Teams チャネルまたはチャット セッションで機密情報を共有するユーザーを防止するポリシーを定義できます。 この保護のしくみの例を次に示します。

- **例 1: メッセージ内の機密情報を保護します**。 Teams チャットまたはチャネル内の機密情報をゲスト (外部ユーザー) と共有しようとしたとします。 これを防ぐために DLP ポリシーが定義されている場合は、外部ユーザーに送信される機密情報を含むメッセージが削除されます。 これは、DLP ポリシーの構成方法に従って、自動的に数秒で行われます。

    > [!NOTE]
    > Microsoft Teams の DLP は、次の権限を持つ Microsoft Teams ユーザーと共有すると、機密コンテンツをブロックします。<br/>- [チームとチャネル](/MicrosoftTeams/guest-access) でのゲスト アクセス。または<br/>- [会議およびチャット](/MicrosoftTeams/manage-external-access) セッションでの外部アクセス。 <p>外部チャット セッションの DLP は、送信者と受信者の両方が Teams Only モードで Microsoft Teams ネイティブ フェデレーションを使用している場合にのみ [機能します](/microsoftteams/manage-external-access)。 TEAMS の DLP は、Skype for Business またはネイティブ以外のフェデレーション チャット セッションとの相互運用のメッセージをブロックしません。 [](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business)

- **例 2: ドキュメント内の機密情報を保護します**。 Microsoft Teams チャネルまたはチャットのゲストとドキュメントを共有しようとすると、そのドキュメントに機密情報が含まれているとします。 これを防ぐために DLP ポリシーが定義されている場合、ドキュメントはそれらのユーザーに対して開かれません。 この場合、保護を適用するには、DLP ポリシーに SharePoint と OneDrive を含める必要があります。 (これは、Microsoft Teams に表示される SharePoint 用 DLP の例であり、Office 365 DLP (Office 365 E3 に含まれる) のライセンスをユーザーに要求しますが、Office 365 Advanced Compliance のライセンスをユーザーに要求しません)。

## <a name="policy-tips-help-educate-users"></a>ポリシー ヒントは、ユーザーの教育に役立ちます

[Exchange、Outlook、Outlook on the](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)web、SharePoint [Online、OneDrive for Business](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)サイト、[および Office](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)デスクトップ クライアントでの DLP の動作と同様に、アクションが DLP ポリシーと競合するとポリシー ヒントが表示されます。 ポリシー ヒントの例を次に示します。

![Teams のブロックされたメッセージ通知](../media/dlp-teams-blockedmessage-notification.png)

この場合、送信者は Microsoft Teams チャネルで社会保障番号を共有しようとした。 [ **実行できる操作] リンクは** 、送信者が問題を解決するためのオプションを提供するダイアログ ボックスを開きます。 この場合、送信者はポリシーを上書きするか、管理者に確認と解決を通知することができます。

![ブロックされたメッセージを解決するためのオプション](../media/dlp-teams-blockedmessage-possibleactions.png)

組織では、ユーザーに DLP ポリシーの上書きを許可できます。 また、DLP ポリシーを構成する場合は、既定のポリシー ヒントを使用するか、組織の [ポリシー ヒント](#to-customize-policy-tips) をカスタマイズできます。

送信者が Teams チャネルで社会保障番号を共有した例に戻り、受信者が見た情報を次に示します。

![ブロックされたメッセージ](../media/dlp-teams-blockedmessage-notification-to-user.png)

**[What's this?** ][](data-loss-prevention-policies.md)リンクは DLP ポリシーに関する記事を開き、メッセージがブロックされた理由を説明するのに役立ちます。

### <a name="to-customize-policy-tips"></a>ポリシーのヒントをカスタマイズするには

このタスクを実行するには、DLP ポリシーを編集する権限を持つロールを割り当てる必要があります。 詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。

1. コンプライアンス センター ( ) &に移動し [https://protection.office.com](https://protection.office.com) 、サインインします。

2. [**データ損失防止ポリシー] を**  >  **選択します**。

3. ポリシーを選択し、[ポリシー設定] の **横にある**[編集] を **選択します**。

4. 新しいルールを作成するか、ポリシーの既存のルールを編集します。<br/>![ポリシーのルールの編集](../media/dlp-teams-editrule.png)<br/>

5. [ユーザー通知 **] タブで** 、[メール テキストの **カスタマイズ** ] または [ポリシー ヒントのテキスト **オプションのカスタマイズ] を選択** します。<br/>![ユーザー通知とポリシーヒントをカスタマイズする](../media/dlp-teams-editrule-usernotifications.png)<br/>  

6. 電子メール通知やポリシー ヒントに使用するテキストを指定し、[保存] を **選択します**。

7. [ポリシー設定 **] タブで** 、[保存] を **選択します**。

変更がデータ センターを通じて動作し、ユーザー アカウントに同期するために約 1 時間を許可します。
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>Microsoft Teams を場所として既存の DLP ポリシーに追加する

このタスクを実行するには、DLP ポリシーを編集する権限を持つロールを割り当てる必要があります。 詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。

1. コンプライアンス センター ( ) &に移動し [https://protection.office.com](https://protection.office.com) 、サインインします。

2. [**データ損失防止ポリシー] を**  >  **選択します**。

3. ポリシーを選択し、[場所] の下の値 **を確認します**。 Teams のチャット **メッセージとチャネル メッセージが表示される** 場合は、すべて設定されています。 編集しない場合は、[編集] を **クリックします**。<br/>![既存のポリシーの場所](../media/dlp-teams-editexistingpolicy.png)<br/>

4. [状態 **] 列** で、Teams チャット メッセージとチャネル メッセージの **ポリシーをオンにします**。<br/>![Teams のチャットとチャネルの DLP](../media/dlp-teams-addteamschatschannels.png)<br/>

5. [場所 **の選択] タブ** で、すべてのアカウントの既定の設定を維持するか、[特定の場所を選択する] **を選択します**。 次の情報を指定できます。
    1. 最大 1000 個の個別アカウントを含めるか除外する
    1. 配布リストとセキュリティ グループを含めるか除外します。 **これはパブリック プレビュー機能です。**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. **[次へ]** を選択します。



6. [**保存**] をクリックします。

変更がデータ センターを通じて動作し、ユーザー アカウントに同期するために約 1 時間を許可します。
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Microsoft Teams の新しい DLP ポリシーを定義する

このタスクを実行するには、DLP ポリシーを編集する権限を持つロールを割り当てる必要があります。 詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。

1. コンプライアンス センター ( ) &に移動し [https://protection.office.com](https://protection.office.com) 、サインインします。

2. [**データ損失防止ポリシー] +**  >    >  **[ポリシーの作成] を選択します**。

3. テンプレートを選択 [し、[](data-loss-prevention-policies.md#dlp-policy-templates)次へ] を **選択します**。<br/>この例では、米国の個人を特定できる情報データ テンプレートを選択しました。<br/>![DLP ポリシーのプライバシー テンプレート](../media/dlp-teams-createnewpolicy-template.png)<br/>

4. [ポリシー **に名前を付け** ] タブで、ポリシーの名前と説明を指定し、[次へ] を **選択します**。

5. [場所 **の選択] タブ** で、すべてのアカウントの既定の設定を維持するか、[特定の場所を選択する] **を選択します**。 次の情報を指定できます。
    1. 最大 1000 個の個別アカウントを含めるか除外する
    1. 配布リストとセキュリティ グループを含めるか除外します。 **これはパブリック プレビュー機能です。**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

![DLP ポリシーの場所](../media/dlp-teams-selectlocationsnewpolicy.png)

> [!NOTE]
> 機密情報を含むドキュメントが Teams で不適切に共有されない場合は **、SharePoint** サイトと **OneDrive** アカウントが Teams チャットメッセージとチャネル メッセージと共にオンになっていることを **確認します**。


6. [ポリシー設定 **] タブ** の[保護するコンテンツの種類をカスタマイズする] で、既定の単純な設定を保持するか、[詳細設定を使用する] を選択して、[次へ] を選択 **します**。 詳細設定を選択した場合は、ポリシーのルールを作成または編集できます。 (このヘルプについては、「簡易設定 [と詳細設定」を参照](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)してください。

7.  [ポリシー **設定] タブ** の **[機密情報** が検出された場合の操作] で、設定を確認します。 (既定のポリシー ヒントと電子メール通知を[](use-notifications-and-policy-tips.md)保持するか、カスタマイズすることもできます)。<br/>![ヒントと通知を含む DLP ポリシー設定](../media/dlp-teams-policysettings-tipsemails.png)<br/>設定の確認または編集が完了したら、[次へ] を **選択します**。

8. [ポリシーの **設定**] タブの [ポリシーを有効にするか、最初にテストするのかを選択しますか **?]** で、ポリシーを有効 [](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)にするか、最初にテストするか、今のところオフにしておき、[次へ] を選択します。<br/>![ポリシーを有効にするかどうかを指定する](../media/dlp-teams-policysettings-turnonnow.png)<br/>

9. [設定 **の確認] タブ** で、新しいポリシーの設定を確認します。 [編集 **] を** 選択して変更を加えます。 完了したら、[作成] を **選択します**。

新しいポリシーがデータセンター経由で動作し、ユーザー アカウントと同期するには、約 1 時間を許可します。

## <a name="prevent-external-access-to-sensitive-documents"></a>機密文書への外部アクセスを防止する

機密情報を含む SharePoint ドキュメントに、既定で SharePoint または Teams から外部ゲストがアクセスできないことを確認するには、次の項目を選択します。

- 新しいファイルを既定で機密性の高いファイルとしてマークすることで、DLP スキャンを実行して共有しても安全とマークされるまで、ドキュメントが [保護されます。](/sharepoint/sensitive-by-default)
- 推奨される DLP ポリシー構造
    - **条件**
        - コンテンツには、次の機密情報の種類が含まれる。 [適用されるすべて選択]
        - Microsoft 365 から組織外のユーザーとコンテンツを共有する
        <br/>![機密性の高いコンテンツの外部共有を検出する DLP 条件](../media/dlp-teams-external-sharing/external-condition.png)<br/>


    - **アクション**
        - 外部ユーザーのコンテンツへのアクセスを制限する
        - メールおよびポリシー ヒントでユーザーに通知する
        - インシデント レポートを管理者に送信する    
        <br/>![機密性の高いコンテンツの外部共有をブロックする DLP アクション](../media/dlp-teams-external-sharing/external-action.png)<br/>

機密情報を含む SharePoint でドキュメントを外部ゲストと共有しようとすると、DLP ポリシーが実行されます。
<br/>![外部共有がブロックされている](../media/dlp-teams-external-sharing/external-sharing-blocked.png)<br/>


ゲストが Teams でドキュメントを開き、外部ブロックを使用すると、DLP ポリシーが実行されます。
<br/>![外部アクセスがブロックされている](../media/dlp-teams-external-sharing/external-access-blocked.png)<br/>

## <a name="related-articles"></a>関連記事

[DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)

[メール通知を送信して、DLP ポリシーのヒントを表示する](use-notifications-and-policy-tips.md)