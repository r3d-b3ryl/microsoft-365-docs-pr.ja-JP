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
description: これで、Microsoft Teams のチャットとチャネルに DLP ポリシーを適用できます。 動作の詳細については、この記事を参照してください。
ms.openlocfilehash: 13d5d73423cc6ad7db76076f6a53dde668b8fa5c
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279365"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>データ損失防止と Microsoft Teams

> [!NOTE]
> データ損失防止機能は、Office 365 E5/A5、Microsoft 365 E5/A5、Microsoft 365 Information Protection and Governance、または Office 365 Advanced Compliance のライセンスを持つユーザー向け Microsoft Teams チャットおよびチャネル メッセージに追加されました。 Office 365 および Microsoft 365 E3 には、SharePoint Online、OneDrive、Exchange Online の DLP 保護が含まれます。 これには、Teams が SharePoint Online と OneDrive を使用してファイルを共有するために、Teams を通じて共有されるファイルも含まれます。
Teams チャットでの DLP 保護のサポートには E5 が必要です。
ライセンス要件の詳細については、「[Microsoft 365 テナントレベル サービスのライセンスに関するガイダンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)」を参照してください。

> [!IMPORTANT]
> Teams の DLP は、ユーザーが Exchange Online にあるメールボックスを持っている場合にのみサポートされます。

## <a name="overview-of-dlp-for-microsoft-teams"></a>Microsoft Teams の DLP の概要

最近、 [データ損失防止](data-loss-prevention-policies.md) (DLP) 機能が拡張され、プライベート チャネル メッセージを含む Microsoft Teams チャットとチャネル **メッセージが含まれます**。

組織に DLP がある場合は、Microsoft Teams チャネルまたはチャット セッションでユーザーが機密情報を共有するポリシーを定義できます。 この保護のしくみの例を次に示します。

- **例 1: メッセージ内の機密情報を保護する**。 Teams のチャットまたはチャネルで、誰かがゲスト (外部ユーザー) と機密情報を共有しようとしたとします。 これを防ぐために DLP ポリシーが定義されている場合は、外部ユーザーに送信される機密情報を含むメッセージが削除されます。 これは、DLP ポリシーの構成方法に従って、自動的に数秒で行われます。

    > [!NOTE]
    > Microsoft Teams の DLP は、次の条件を持つ Microsoft Teams ユーザーと共有すると、機密コンテンツをブロックします。<br/>- [チームとチャネル](https://docs.microsoft.com/MicrosoftTeams/guest-access) でのゲスト アクセスまたは<br/>- [会議およびチャット](https://docs.microsoft.com/MicrosoftTeams/manage-external-access) セッションでの外部アクセス。 <p>外部チャット セッションの DLP は、送信者と受信者の両方が Teams Only モードで [、Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-external-access)ネイティブ フェデレーションを使用している場合にのみ機能します。 Teams の DLP は、Skype for Business またはネイティブ以外のフェデレーション チャット セッションとの相互運用のメッセージをブロックしません。 [](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business)

- **例 2: ドキュメント内の機密情報を保護する**。 Microsoft Teams チャネルまたはチャットのゲストとドキュメントを共有しようとして、ドキュメントに機密情報が含まれているとします。 これを防ぐために DLP ポリシーが定義されている場合、ドキュメントはそれらのユーザーに対して開かれません。 この場合、保護を適用するには、DLP ポリシーに SharePoint と OneDrive を含める必要があります。 (これは、Microsoft Teams に表示される SharePoint 用 DLP の例であり、そのため、ユーザーには Office 365 DLP (Office 365 E3 に含まれる) のライセンスが必要ですが、ユーザーに Office 365 Advanced Compliance のライセンスを与える必要はありません)。

## <a name="policy-tips-help-educate-users"></a>ポリシー ヒントは、ユーザーの教育に役立ちます

[Exchange、Outlook、Web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)上の Outlook、SharePoint [Online、OneDrive for Business](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)サイト、および[Office](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)デスクトップ クライアントでの DLP の動作と同様に、アクションが DLP ポリシーと競合すると、ポリシー ヒントが表示されます。 ポリシー ヒントの例を次に示します。

![Teams でのブロックされたメッセージ通知](../media/dlp-teams-blockedmessage-notification.png)

この場合、送信者は Microsoft Teams チャネルで社会保障番号を共有しようとした。 [ **操作方法] リンクは** 、送信者が問題を解決するためのオプションを提供するダイアログ ボックスを開きます。 この場合、送信者はポリシーを上書きするか、ポリシーを確認して解決することを管理者に通知できます。

![ブロックされたメッセージを解決するオプション](../media/dlp-teams-blockedmessage-possibleactions.png)

組織では、ユーザーに DLP ポリシーの上書きを許可することができます。 また、DLP ポリシーを構成するときに、既定のポリシー ヒントを使用するか、組織の [ポリシー](#to-customize-policy-tips) ヒントをカスタマイズできます。

この例に戻り、送信者が Teams チャネルで社会保障番号を共有しました。受信者が確認した情報を次に示します。

![ブロックされたメッセージ](../media/dlp-teams-blockedmessage-notification-to-user.png)

**[What's this?** ][](data-loss-prevention-policies.md)リンクは DLP ポリシーに関する記事を開きます。これは、メッセージがブロックされた理由を説明するのに役立ちます。

### <a name="to-customize-policy-tips"></a>ポリシー ヒントをカスタマイズするには

このタスクを実行するには、DLP ポリシーを編集するアクセス許可を持つ役割が割り当てられている必要があります。 詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。

1. セキュリティ & コンプライアンス センター ( ) に移動し [https://protection.office.com](https://protection.office.com) 、サインインします。

2. データ損失 **防止ポリシーを選択**  >  **します**。

3. ポリシーを選択し、[ポリシー設定] **の横** にある [編集] を **選択します**。

4. 新しいルールを作成するか、ポリシーの既存のルールを編集します。<br/>![ポリシーのルールの編集](../media/dlp-teams-editrule.png)<br/>

5. [ユーザー通知 **] タブで** 、[メール テキストの **カスタマイズ** ] または [ポリシー ヒント テキスト オプションのカスタマイズ] **を選択** します。<br/>![ユーザー通知とポリシー ヒントをカスタマイズする](../media/dlp-teams-editrule-usernotifications.png)<br/>  

6. 電子メール通知やポリシー ヒントに使用するテキストを指定し、[保存] を選択 **します**。

7. [ポリシー設定 **] タブで、[** 保存] を **選択します**。

変更がデータ センターを経由してユーザー アカウントに同期されるのに約 1 時間を許可します。
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>既存の DLP ポリシーに場所として Microsoft Teams を追加する

このタスクを実行するには、DLP ポリシーを編集するアクセス許可を持つ役割が割り当てられている必要があります。 詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。

1. セキュリティ & コンプライアンス センター ( ) に移動し [https://protection.office.com](https://protection.office.com) 、サインインします。

2. データ損失 **防止ポリシーを選択**  >  **します**。

3. ポリシーを選択し、[場所] の下の値 **を確認します**。 Teams のチャット **メッセージとチャネル メッセージが表示** される場合は、すべて設定されています。 If you don't, click **Edit**.<br/>![既存のポリシーの場所](../media/dlp-teams-editexistingpolicy.png)<br/>

4. [状態 **] 列** で、Teams チャットおよびチャネル メッセージの **ポリシーを有効にします**。<br/>![Teams のチャットとチャネルの DLP](../media/dlp-teams-addteamschatschannels.png)<br/>

5. [場所 **の選択]** タブで、すべてのアカウントの既定の設定を維持するか、[特定の場所を選択する **] を選択します**。 次の情報を指定できます。
    1. 最大 1,000 個の個別アカウントを含める、または除外する
    1. 含める、または除外する配布リストとセキュリティ グループ。 **これはパブリック プレビュー機能です。**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. **[次へ]** を選択します。



6. [**保存**] をクリックします。

変更がデータ センターを経由してユーザー アカウントに同期されるのに約 1 時間を許可します。
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Microsoft Teams の新しい DLP ポリシーを定義する

このタスクを実行するには、DLP ポリシーを編集するアクセス許可を持つ役割が割り当てられている必要があります。 詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。

1. セキュリティ & コンプライアンス センター ( ) に移動し [https://protection.office.com](https://protection.office.com) 、サインインします。

2. データ **損失防止ポリシーを**  >  **選択**  >  **し、ポリシーを作成します**。

3. テンプレートを選択 [し](data-loss-prevention-policies.md#dlp-policy-templates)、[次へ] を **選択します**。<br/>この例では、米国の個人を特定できる情報データ テンプレートを選択しました。<br/>![DLP ポリシーのプライバシー テンプレート](../media/dlp-teams-createnewpolicy-template.png)<br/>

4. On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.

5. [場所 **の選択]** タブで、すべてのアカウントの既定の設定を維持するか、[特定の場所を選択する **] を選択します**。 次の情報を指定できます。
    1. 最大 1,000 個の個別アカウントを含める、または除外する
    1. 含める、または除外する配布リストとセキュリティ グループ。 **これはパブリック プレビュー機能です。**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

![DLP ポリシーの場所](../media/dlp-teams-selectlocationsnewpolicy.png)

> [!NOTE]
> 機密情報を含むドキュメントが Teams で不適切に共有されない場合は **、SharePoint** サイトと **OneDrive** アカウントが Teams のチャットおよびチャネル メッセージと共にオンになっていることを確認 **します**。


6. [ポリシー **設定]** タブの[保護するコンテンツの種類のカスタマイズ] で、既定の簡単な設定を維持するか、[詳細設定を使用] を選択して 、[次へ] を選択 **します**。 詳細設定を選択した場合は、ポリシーのルールを作成または編集できます。 (このヘルプについては、「簡単な設定と詳細設定」 [を参照してください](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings))。

7.  [ポリシー **設定] タブ** の[機密情報が検出された場合の操作] で、設定を確認します。 (ここでは、既定のポリシー ヒントと電子メール[](use-notifications-and-policy-tips.md)通知を保持するか、カスタマイズすることができます)。<br/>![ヒントと通知を含む DLP ポリシー設定](../media/dlp-teams-policysettings-tipsemails.png)<br/>設定の確認または編集が完了したら、[次へ] を選択 **します**。

8. On the **Policy settings** tab, under Do you want on the policy or test things **out first?** choose whether to turn the policy on, [test it first,](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)or keep it turned off for now, and then choose **Next**.<br/>![ポリシーを有効にするかどうかを指定する](../media/dlp-teams-policysettings-turnonnow.png)<br/>

9. [設定 **の確認] タブで** 、新しいポリシーの設定を確認します。 [編集 **] を選択** して変更します。 完了したら、[作成] を選択 **します**。

新しいポリシーがデータ センターを経由して動作し、ユーザー アカウントと同期するには、約 1 時間を許可します。

## <a name="prevent-external-access-to-sensitive-documents"></a>機密ドキュメントへの外部アクセスを防止する

機密情報を含む SharePoint ドキュメントに、既定で SharePoint または Teams から外部ゲストがアクセスできないことを確認するには、次の項目を選択します。

- DLP スキャンまでドキュメントを保護し、新しいファイルを既定で機密としてマークすることで、ドキュメントを共有しても安全だと [マークできます。](https://docs.microsoft.com/sharepoint/sensitive-by-default)
- 推奨される DLP ポリシー構造
    - **条件**
        - コンテンツには、次の機密情報の種類が含まれる: [適用されるすべて選択]
        - Microsoft 365 から組織外のユーザーとコンテンツを共有する
        <br/>![機密コンテンツの外部共有を検出する DLP 条件](../media/dlp-teams-external-sharing/external-condition.png)<br/>


    - **アクション**
        - 外部ユーザーのコンテンツへのアクセスを制限する
        - 電子メールとポリシー ヒントを使用してユーザーに通知する
        - インシデント レポートを管理者に送信する    
        <br/>![機密コンテンツの外部共有をブロックする DLP アクション](../media/dlp-teams-external-sharing/external-action.png)<br/>

機密情報を含む SharePoint のドキュメントを外部ゲストと共有しようとするときに動作する DLP ポリシー:
<br/>![外部共有のブロック](../media/dlp-teams-external-sharing/external-sharing-blocked.png)<br/>


ゲストが外部ブロックを使用して Teams でドキュメントを開く際に有効な DLP ポリシー:
<br/>![外部アクセスのブロック](../media/dlp-teams-external-sharing/external-access-blocked.png)<br/>

## <a name="related-articles"></a>関連記事

[DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)

[メール通知を送信して、DLP ポリシーのヒントを表示する](use-notifications-and-policy-tips.md)
