---
title: 検疫ポリシー
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 管理者は、検疫ポリシーを使用して、検疫されたメッセージに対してユーザーが実行できる操作を制御する方法を学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01a4d5acb9edfa0906695329489439d3ce6af298
ms.sourcegitcommit: ab32c6e19af08837aaa84a058653c3a209d366ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2022
ms.locfileid: "67445140"
---
# <a name="quarantine-policies"></a>検疫ポリシー

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象:**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) の検疫ポリシー (以前は _検疫タグ_ と呼ばれていました) とMicrosoft Defender for Office 365 を使うと、管理者はメッセージが検疫された理由に基づいて、検疫されたメッセージに対してユーザーが実行できる操作を制御できます。 この機能は、Exchange Onlineメールボックスを使用するすべての Microsoft 365 組織で使用できます。

従来、ユーザーは、メッセージが検疫された理由に基づいて、検疫メッセージの対話のレベルを許可または拒否していました。 たとえば、スパム対策フィルターによって検疫されたメッセージをスパムまたはバルクとして表示および解放できますが、高確度のフィッシングやマルウェアとして検疫されたメッセージを表示または解放することはできません。

[サポートされている保護機能](#step-2-assign-a-quarantine-policy-to-supported-features)の場合、検疫ポリシーでは、検疫と _検疫通知_ で、ユーザーが自分のメッセージ (受信者であるメッセージ) に対して実行できる操作が指定されます。 [検疫通知](use-spam-notifications-to-release-and-report-quarantined-messages.md) は、エンド ユーザーのスパム通知の代わりに使用されます。 検疫通知には、サポートされているすべての保護機能 (スパム対策ポリシーおよびフィッシング対策ポリシーの判定だけでなく) の検疫済みメッセージに関する情報が含まれます。

履歴ユーザー機能を適用する既定の検疫ポリシーは、メッセージを検疫するサポートされている保護機能のアクションに自動的に割り当てられます。 または、カスタム検疫ポリシーを作成し、サポートされている保護機能に割り当てて、ユーザーがこのような種類の検疫済みメッセージに対して特定のアクションを実行できないようにすることもできます。

個々の検疫ポリシーのアクセス許可は、次の事前設定されたアクセス許可グループに組み合わされます:

- アクセスなし
- 制限付きアクセス
- フル アクセス

事前設定されたアクセス許可グループに含まれる個々の検疫ポリシーのアクセス許可を次の表に示します:

|アクセス許可|アクセスなし|制限付きアクセス|フル アクセス|
|---|:---:|:---:|:---:|
|**送信者をブロック** (_PermissionToBlockSender_)||![チェック マーク。](../../media/checkmark.png)|![チェック マーク。](../../media/checkmark.png)|
|**削除** (_PermissionToDelete_)||![チェック マーク。](../../media/checkmark.png)|![チェック マーク。](../../media/checkmark.png)|
|**プレビュー** (_PermissionToPreview_)||![チェック マーク。](../../media/checkmark.png)|![チェック マーク。](../../media/checkmark.png)|
|**受信者が検疫からメッセージを解放することを許可する** (_PermissionToRelease_)<sup>\*</sup>|||![チェック マーク。](../../media/checkmark.png)|
|**受信者が検疫アクセス許可からメッセージを解放する要求を許可する** (_PermissionToRequestRelease_) を参照してください。||![チェック マーク](../../media/checkmark.png)||

<sup>\*</sup>**受信者が検疫からメッセージを解放することを許可** するアクセス許可は、マルウェア対策ポリシーやスパム対策ポリシーの高信頼フィッシング判定では受け入れられません。 ユーザーは、独自のマルウェアや信頼度の高いフィッシング メッセージを検疫から解放できません。 [受信者を許可する] を使用 **して、検疫アクセス許可から解放するメッセージを要求** できます。

次の表に、既定の検疫ポリシー、関連するアクセス許可グループ、および検疫通知を有効にするかどうかを示します。

|既定の検疫ポリシー|使用されるアクセス許可グループ|検疫通知が有効になっていますか?|
|---|:---:|:---:|
|AdminOnlyAccessPolicy|アクセスなし|いいえ|
|DefaultFullAccessPolicy|フル アクセス|いいえ|
|NotificationEnabledPolicy<sup>\*</sup>|フル アクセス|はい|

事前設定されたアクセス許可グループの既定のアクセス許可が気に入らない場合、または検疫通知を有効にする場合は、カスタム検疫ポリシーを作成して使用します。 各アクセス許可の動作の詳細については、この記事の後半の「[検疫ポリシーのアクセス許可の詳細](#quarantine-policy-permission-details)」セクションを参照してください。

Microsoft 365 Defender ポータルまたは PowerShell で検疫ポリシーを作成して割り当てます (Exchange Online メールボックスを持つ Microsoft 365 組織の場合は Exchange Online PowerShell、Exchange Online メールボックスがない EOP 組織ではスタンドアロン EOP PowerShell)。

> [!NOTE]
> 検疫済みメッセージが期限切れになるまでに検疫に保持される期間は、スパム対策ポリシーの **この日数 (_QuarantineRetentionPeriod_) スパムの検疫を保持** によって制御されます。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。
>
> サポートされている保護機能に割り当てられている検疫ポリシーを変更すると、_変更後_ に検疫されるメッセージに変更が影響します。 その保護機能によって以前に検疫されたメッセージは、新しい検疫ポリシーの割り当て設定の影響を受けません。

## <a name="full-access-permissions-and-quarantine-notifications"></a>フル アクセス許可と検疫通知

<sup>\*</sup> NotificationEnabledPolicy という名前の検疫ポリシーは、すべての環境に存在するわけではありません。 組織が次の要件の両方を満たしている場合は、NotificationEnabledPolicy 検疫ポリシーが適用されます:

- 組織は、検疫ポリシー機能が有効になる前に存在していた (2021 年 7 月後半/8 月初旬)。
- 1 つ以上の [スパム対策ポリシー](configure-your-spam-filter-policies.md) (既定のスパム対策ポリシーまたはカスタムスパム対策ポリシー) があり、[**エンド ユーザーのスパム通知を有効にする]** 設定がオンになっている。

前述のように、検疫ポリシーの検疫通知は、スパム対策ポリシーでオンまたはオフに使用したエンド ユーザーのスパム通知を置き換えます。 DefaultFullAccessPolicy という名前の組み込みの検疫ポリシーは、検疫されたメッセージの履歴 _アクセス許可_ を複製しますが、検疫ポリシーでは _検疫通知_ は有効になりません。 また、組み込みのポリシーを変更できないため、DefaultFullAccessPolicy で検疫通知を有効にすることはできません。

DefaultFullAccessPolicy のアクセス許可を提供するために、検疫通知が有効になっている場合に、それを必要とする組織 (エンド ユーザースパム通知が有効になっている組織) に対して DefaultFullAccessPolicy の代わりに使用する NotificationEnabledPolicy という名前のポリシーが作成されました。

スパム対策ポリシーでエンド ユーザーのスパム通知を有効にしたことがない新しい組織または以前の組織の場合、NotificationEnabledPolicy という名前の検疫ポリシーはありません。 検疫通知を有効にする方法は、検疫通知が有効になっているカスタム検疫ポリシーを作成して使用する方法です。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 [**検疫**] ページに直接移動するには、<https://security.microsoft.com/quarantinePolicies> を使用します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- 検疫ポリシーを表示、作成、変更、または削除するには、Microsoft 365 Defender ポータルの **組織管理**、**セキュリティ管理者**、または **検疫管理者** の各ロールを有するメンバーである必要があります。 詳細については、「[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)」を参照してください。

## <a name="step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal"></a>手順 1: Microsoft 365 Defender ポータルで検疫ポリシーを作成する

1. [Microsoft 365 Defender ポータル](https://security.microsoft.com)の [**ルール**] セクションで、[**メールとコラボレーション**] \> [**ポリシーとルール**] \> [**脅威ポリシー**] \> [**検疫ポリシー**] に移動します。 または、[ **検疫ポリシー]** ページに直接移動するには、 <https://security.microsoft.com/quarantinePolicies>.

   :::image type="content" source="../../media/mdo-quarantine-policy-page.png" alt-text="Microsoft 365 Defender ポータルの [検疫ポリシー] ページ。" lightbox="../../media/mdo-quarantine-policy-page.png":::

2. [ **検疫ポリシー] ページで** 、[カスタム ポリシーの追加] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **カスタム ポリシーを追加します**。

3. **新しいポリシー** ウィザードが開きます。 [**ポリシー名**] ページで、[**ポリシー名**] ボックスに簡単で一意の名前を入力します。 今後の手順では、名前で検疫ポリシーを識別して選択する必要があります。 完了したら、**[次へ]** をクリックします。

4. [**受信者メッセージ アクセス**] ページで、次のいずれかの値を選択します:
   - **制限付きアクセス**: このアクセス許可グループに含まれる個々のアクセス許可については、この記事の前半で説明しました。
   - **特定のアクセスを設定する (詳細設定)**: この値を使用して、カスタム アクセス許可を指定します。 表示される次の設定を構成します:
     - **解放アクション選択の基本設定**: 次のいずれかの値を選択します:
       - 空白: これが既定値です。
       - **受信者が検疫からメッセージを解放することを許可する**
       - **受信者がメッセージの検疫からの解放を許可する**
     - **受信者が検疫済みメッセージに対して実行できる追加のアクションを選択する**: 次の値の一部、すべてを選択するか、どれも選択しません:
       - **削除**
       - **プレビュー**
       - **差出人をブロックする**

   これらのアクセス許可と、検疫されたメッセージと検疫通知への影響については、この記事の後半の「[検疫ポリシーのアクセス許可の詳細](#quarantine-policy-permission-details)」セクションで説明します。

   完了したら、**[次へ]** をクリックします。

5. [**エンド ユーザー スパム通知**] ページで、[**有効にする**] を選択して検疫通知 (以前はエンド ユーザー スパム通知と呼ばれていました) を有効にします。 完了したら、**[次へ]** をクリックします。

   > [!NOTE]
   > 前述のように、組み込みのポリシー (AdminOnlyAccessPolicy または DefaultFullAccessPolicy) には検疫された通知が有効になっていないため、ポリシーを変更することはできません。

6. [**ポリシーの確認**] ページで、設定を確認します。 各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 または、**[戻る]** をクリックするか、ウィザードで特定のページを選択します。

   完了したら、**[送信]** をクリックします。

7. 表示された [確認]ページで、**[完了]** をクリックします。

これで、[手順 2](#step-2-assign-a-quarantine-policy-to-supported-features) セクションで説明されているように、検疫ポリシーを検疫機能に割り当てる準備ができました。

### <a name="create-quarantine-policies-in-powershell"></a>PowerShell で検疫ポリシーを作成する

PowerShell を使用して検疫ポリシーを作成する場合は、Exchange Online PowerShell または Exchange Online Protection PowerShell に接続し、**New-QuarantinePolicy** コマンドレットを使用します。

> [!NOTE]
> _ESNEnabled_ パラメーターと値 `$true` を使用しない場合、検疫通知はオフになります。

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a>EndUserQuarantinePermissionsValue パラメーターを使用する

_EndUserQuarantinePermissionsValue_ パラメーターを使用して検疫ポリシーを作成するには、次の構文を使用します:

```powershell
New-QuarantinePolicy -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236> [-EsnEnabled $true]
```

_EndUserQuarantinePermissionsValue_ パラメーターは、バイナリ値から変換された 10 進値を使用します。 バイナリ値は、特定の順序で使用可能なエンド ユーザー検疫アクセス許可に対応します。 各アクセス許可で、値 1 は True、値 0 は False となります。

個々のアクセス許可に必要な順序と値を次の表に示します:

|アクセス許可|10 進値|バイナリ値|
|---|:---:|:---:|
|PermissionToViewHeader<sup>\*</sup>|128|10000000|
|PermissionToDownload<sup>\*\*</sup>|64|01000000|
|PermissionToAllowSender<sup>\*\*</sup>|32|00100000|
|PermissionToBlockSender|16|00010000|
|PermissionToRequestRelease<sup>\*\*\*</sup>|8 |00001000|
|PermissionToRelease<sup>\*\*\*</sup>|4|00000100|
|PermissionToPreview|2|00000010|
|PermissionToDelete|1|00000001|

<sup>\*</sup> 値 0 の場合、検疫されたメッセージの詳細の [ **メッセージ ヘッダーの表示**] ボタンは非表示になりません (ボタンが常に使用できます)。

<sup>\*\*</sup> この設定は使用されません (値 0 でも 1 でも何も行われません)。

<sup>\*\*\*</sup> これらの値の両方を 1 に設定しないでください。 一方を 1 に設定し、もう一方を 0 に設定するか、両方を 0 に設定します。

制限付きアクセス許可の場合、必要な値は次のとおりです:

|アクセス許可|制限付きアクセス|
|---|:--:|
|PermissionToViewHeader|0|
|PermissionToDownload|0|
|PermissionToAllowSender|0|
|PermissionToBlockSender|1|
|PermissionToRequestRelease|1|
|PermissionToRelease|0|
|PermissionToPreview|1|
|PermissionToDelete|1|
|バイナリ値|00011011|
|使用する 10 進値|27|

この例では、前の表で説明したように、制限付きアクセス許可を割り当てる、検疫通知がオンになっている LimitedAccess という名前の新しい検疫ポリシーを作成します。

```powershell
New-QuarantinePolicy -Name LimitedAccess -EndUserQuarantinePermissionsValue 27 -EsnEnabled $true
```

カスタムアクセス許可の場合は、前の表を使用して、必要なアクセス許可に対応するバイナリ値を取得します。 バイナリ値を 10 進値に変換し、 _EndUserQuarantinePermissionsValue_ パラメーターに 10 進値を使用します。 パラメーター値にバイナリ値を使用しないでください。

構文とパラメーターの詳細については、「[New-QuarantinePolicy](/powershell/module/exchange/new-quarantinepolicy)」を参照してください。

## <a name="step-2-assign-a-quarantine-policy-to-supported-features"></a>手順 2: サポートされている機能に検疫ポリシーを割り当てる

メール メッセージを検疫する _サポートされている_ 保護機能では、使用可能な検疫アクションに検疫ポリシーを割り当てることができます。 次の表に、検疫メッセージを検疫する機能と検疫ポリシーの可用性について説明します:

|特徴|検疫ポリシーがサポートされていますか?|使用される既定の検疫ポリシー|
|---|:---:|---|
|[スパム対策ポリシー](configure-your-spam-filter-policies.md) <ul><li>**スパム** (_SpamAction_)</li><li>**高確度迷惑メール** (_HighConfidenceSpamAction_)</li><li>**フィッシング** (_PhishSpamAction_)</li><li>**高確度のフィッシング** (_HighConfidencePhishAction_)</li><li>**バルク** (_BulkSpamAction_)</li></ul>|はい|<ul><li>DefaultFullAccessPolicy<sup>\*</sup> (フル アクセス)</li><li>DefaultFullAccessPolicy<sup>\*</sup> (フル アクセス)</li><li>DefaultFullAccessPolicy<sup>\*</sup> (フル アクセス)</li><li>AdminOnlyAccessPolicy (アクセスなし)</li><li>DefaultFullAccessPolicy<sup>\*</sup> (フル アクセス)</li></ul>|
|フィッシング詐欺対策ポリシー: <ul><li>[スプーフィング インテリジェンスに対する保護](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</li><li>[Defender for Office 365 の偽装に対する保護](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<ul><li>**偽装されたユーザーとしてメッセージが検出された場合** (_TargetedUserProtectionAction_)</li><li>**偽装されたドメインとしてメッセージが検出された場合** (_TargetedDomainProtectionAction_)</li><li>**メールボックス インテリジェンスにより偽装されたユーザーであることを検出した場合** (_MailboxIntelligenceProtectionAction_)</li></ul></li></ul>|はい|<ul><li>DefaultFullAccessPolicy<sup>\*</sup> (フル アクセス)</li><li>偽装に対する保護:<ul><li>DefaultFullAccessPolicy<sup>\*</sup> (フル アクセス)</li><li>DefaultFullAccessPolicy<sup>\*</sup> (フル アクセス)</li><li>DefaultFullAccessPolicy<sup>\*</sup> (フル アクセス)</li></ul></li></ul>|
|[マルウェア対策ポリシー](configure-anti-malware-policies.md): 検出されたすべてのメッセージは常に検疫されます。|はい|AdminOnlyAccessPolicy (アクセスなし)|
|[安全な添付ファイル保護](safe-attachments.md): <ul><li>安全な添付ファイル ポリシーによってマルウェアとして検疫された添付ファイルを含むメール メッセージ (_Enable_ と _Action_)</li><li>[SharePoint、OneDrive、Microsoft Teamsの安全な添付ファイル](mdo-for-spo-odb-and-teams.md)によりマルウェアとして検疫されたファイル</li></ul>|<ul><li>はい</li><li>いいえ</li></ul>|<ul><li>AdminOnlyAccessPolicy (アクセスなし)</li><li>該当なし</li></ul>|
|アクションを含む [メール フロー ルール](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (トランスポート ルールとも呼ばれます): **メッセージをホストされた検疫** (_検疫_) に配信します。|いいえ|該当なし|

<sup>\*</sup>[この記事で既出のように](#full-access-permissions-and-quarantine-notifications)、組織では DefaultFullAccessPolicy の代わりに NotificationEnabledPolicy を使用する場合があります。 これら 2 つの検疫ポリシーの唯一の違いは、検疫通知が、NotificationEnabledPolicy ではオンになり、DefaultFullAccessPolicy ではオフになっている点です。

既定の検疫ポリシー、事前設定されたアクセス許可グループ、およびアクセス許可については、 [この記事の冒頭](#quarantine-policies) と [この記事の後半](#preset-permissions-groups)で説明します。

> [!NOTE]
> 既定の検疫ポリシーによって提供される (または提供されていない) 既定のエンド ユーザーのアクセス許可と検疫通知に満足している場合は、何もする必要はありません。 ユーザー検疫されたメッセージのエンド ユーザー機能 (使用可能なボタン) を追加または削除する場合、または検疫通知を有効にし、検疫通知で同じ機能を追加または削除する場合は、検疫アクションに別の検疫ポリシーを割り当てることができます。

## <a name="assign-quarantine-policies-in-supported-policies-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルでサポートされているポリシーで、検疫ポリシーを割り当てる

> [!NOTE]
> ユーザーは、検疫ポリシーの構成方法に関係なく、マルウェア (マルウェア対策ポリシー) または高信頼フィッシング (スパム対策ポリシー) として検疫された独自のメッセージをリリースできません。 管理者は、検疫済みマルウェアまたは信頼度の高いフィッシング メッセージのリリースをユーザーが要求できるように、検疫ポリシーを構成できます。

### <a name="anti-spam-policies"></a>スパム対策ポリシー

1. [Microsoft 365 Defender ポータル](https://security.microsoft.com)で、[**ポリシー**] セクションの [**メールとコラボレーション**] \> [**ポリシーとルール**] \> [**脅威ポリシー**] \> [**スパム対策**] に移動します。

   または、[**スパム対策ポリシー**] ページに直接移動するには、<https://security.microsoft.com/antispam> を使用します。

2. [**スパム対策ポリシー**] ページで、以下のいずれかの値を探します:
   - 既存の **受信** スパム対策ポリシーを見つけて選択します。
   - 新しい **受信** スパム対策ポリシーを作成します。

3. 次のいずれかの手順を実行します。
   - **既存のものを編集する**: ポリシーの名前をクリックしてポリシーを選択します。 ポリシーの詳細ポップアップで、[**アクション**] セクションに移動し、[**アクションの編集**] をクリックします。
   - **新規作成**: 新しいポリシー ウィザードで、[**アクション**] ページに移動します。

4. [**アクション**] ページで、[**検疫メッセージ**] アクションを伴うすべての判定には、対応する検疫ポリシーを選択するための [**検疫ポリシー選択**] のボックスも表示されます。

   **注**: 新しいポリシーを作成すると、空白の [**検疫ポリシーの選択**] の値は、その判定の既定の検疫ポリシーが使用されることを示します。 後でポリシーを編集すると、前の表で説明したように、空白の値が実際の既定の検疫ポリシー名に置き換えられます。

   :::image type="content" source="../../media/quarantine-tags-in-anti-spam-policies.png" alt-text="スパム対策ポリシーの検疫ポリシーの選択" lightbox="../../media/quarantine-tags-in-anti-spam-policies.png":::

スパム対策ポリシーの作成と変更に関する詳細な手順については、「[EOP でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。

#### <a name="anti-spam-policies-in-powershell"></a>PowerShell のスパム対策ポリシー

PowerShell を使用してスパム対策ポリシーで検疫ポリシーを割り当てる場合は、Exchange Online PowerShell または Exchange Online Protection PowerShell に接続し、次の構文を使用します:

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>"> [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

**注意**:

- _PhishSpamAction_ パラメーターと _HighConfidencePhishAction_ パラメーターの既定値は "Quarantine" であるため、PowerShell で新しいスパム フィルター ポリシーを作成するときにこれらのパラメーターを使用する必要はありません。 新規または既存のスパム対策ポリシーの _SpamAction_、_HighConfidenceSpamAction_、_BulkSpamAction_ の各パラメーターの場合、検疫ポリシーは、値が "Quarantine" の場合にのみ有効です。

  既存のスパム対策ポリシーで重要なパラメーター値を確認するには、次のコマンドを実行します:

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*SpamAction,HighConfidencePhishAction,*QuarantineTag
  ```

  Standard と Strict の既定のアクション値と推奨されるアクションの値の詳細については、「[EOP スパム対策ポリシーの設定](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)」を参照してください。

- 新しいスパム対策ポリシーを作成すると、対応する検疫ポリシー パラメーターのないスパム フィルターの判定は、その判定の [既定の検疫ポリシー](#step-2-assign-a-quarantine-policy-to-supported-features) が使用されることを意味します。

  既定の検疫ポリシーをカスタム検疫ポリシーに置き換える必要があるのは、特定のスパム フィルター判定の検疫済みメッセージの既定のエンド ユーザー機能を変更する場合のみです。

- PowerShell の新しいスパム対策ポリシーでは、**New-HostedContentFilterPolicy** コマンドレットを使用したスパム フィルター ポリシー (設定) と、**New-HostedContentFilterRule** コマンドレットを使用した排他的スパム フィルター規則 (受信者フィルター) が必要です。 手順については、「[PowerShell を使用してスパム対策ポリシーを作成する](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)」を参照してください。

この例では、次のような設定で Research Development という名前のスパム フィルター ポリシーを作成します:

- すべてのスパム フィルターの判定のアクションは "Quarantine" に設定されます。
- [**アクセスなし**] のアクセス許可を割り当てる NoAccess という名前のカスタム検疫ポリシーは、既定で、[**アクセスなし**] のアクセス許可がまだ割り当てられていない既定の検疫ポリシーに置き換えられます。

```powershell
New-HostedContentFilterPolicy -Name "Research Department" -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

構文とパラメーターの詳細については、「[New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy)」を参照してください。

この例では、Human Resources という名前の既存のスパム フィルター ポリシーを変更します。 スパム検疫の判定のアクションは "Quarantine" に設定され、NoAccess という名前のカスタム検疫ポリシーが割り当てられます。

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

構文とパラメーターの詳細については、「[Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)」を参照してください。

### <a name="anti-phishing-policies"></a>フィッシング対策ポリシー

スプーフィング インテリジェンスは、EOP と Defender for Office 365 で使用可能です。 ユーザー偽装に対する保護、ドメイン偽装に対する保護、メールボックス インテリジェンスは、Defender for Office 365 でのみ使用可能です。 詳細については、「[Microsoft 365 でのフィッシング詐欺対策ポリシー](set-up-anti-phishing-policies.md)」を参照してください。

1. [Microsoft 365 Defender ポータル](https://security.microsoft.com)で、[**ポリシー**] セクションの [**メールとコラボレーション**] \> [**ポリシーとルール**] \> [**脅威ポリシー**] \> [**フィッシング対策**] に移動します。

   または、[**スパム対策ポリシー**] ページに直接移動するには、<https://security.microsoft.com/antiphishing> を使用します。

2. [**フィッシング対策**] ページで、次のいずれかの手順を実行します:
   - 既存のフィッシング対策ポリシーを見つけて選択する。
   - 新しいフィッシング対策ポリシーを作成する。

3. 次のいずれかの手順を実行します。
   - **既存のものを編集する**: ポリシーの名前をクリックしてポリシーを選択します。 表示された詳細のポップアップで、**[保護設定]** セクションを選択し、**[保護設定の編集]** をクリックします。
   - **新規作成**: 新しいポリシー ウィザードで、[**アクション**] ページに移動します。

4. [**保護の設定]** ページで、次の設定がオンになっていて、必要に応じて構成されていることを確認します:
   - **保護を有効にしたユーザー**: ユーザーを指定します。
   - **保護が有効なドメイン**: [**自分が所有するドメインを含める**] または [**カスタム ドメインを含める**] を選択し、ドメインを指定します。
   - **メールボックス インテリジェンスを有効にする**
   - **偽装に対する保護のインテリジェンスを有効にする**
   - **スプーフィング インテリジェンスを有効にする**

5. 次のいずれかの手順を実行します。
   - **既存のものを編集する**: ポリシーの詳細ポップアップで、[**アクション**] セクションに移動し、[**アクションの編集]** をクリックします。
   - **新規作成**: 新しいポリシー ウィザードで、[**アクション**] ページに移動します。

6. [**アクション**] ページで、[**メッセージの検疫**] アクションを持つすべての判定には、対応する 検疫ポリシーを選択するための [**検疫ポリシーの適用**] ボックスも表示されます。

   **注**: 新しいポリシーを作成する際に **[検疫ポリシーの適用]** の値が空なのは、そのアクションの既定の検疫ポリシーが使用されることを示します。 後でポリシーを編集すると、前の表で説明したように、空白の値が実際の既定の検疫ポリシー名に置き換えられます。

   :::image type="content" source="../../media/quarantine-tags-in-anti-phishing-policies.png" alt-text="フィッシング対策ポリシーの検疫ポリシーの選択" lightbox="../../media/quarantine-tags-in-anti-phishing-policies.png":::

フィッシング対策ポリシーの作成と変更に関する完全な手順については、次のトピックを参照してください:

- [EOP でのスパム対策ポリシーの構成](configure-anti-phishing-policies-eop.md)
- [詳細については、「Microsoft Defender for Office 365 のフィッシング対策ポリシーを構成する」を参照してください。](configure-mdo-anti-phishing-policies.md)

#### <a name="anti-phishing-policies-in-powershell"></a>PowerShell のフィッシング対策ポリシー

PowerShell を使用してフィッシング対策ポリシーで検疫ポリシーを割り当てる場合は、PowerShell Exchange Online または Exchange Online Protection PowerShell に接続し、次の構文を使用します:

```powershell
<New-AntiPhishPolicy -Name "<Unique name>" | Set-AntiPhishPolicy -Identity "<Policy name>"> [-EnableSpoofIntelligence $true] [-AuthenticationFailAction Quarantine] [-SpoofQuarantineTag <QuarantineTagName>] [-EnableMailboxIntelligence $true] [-EnableMailboxIntelligenceProtection $true] [-MailboxIntelligenceProtectionAction Quarantine] [-MailboxIntelligenceQuarantineTag <QuarantineTagName>] [-EnableOrganizationDomainsProtection $true] [-EnableTargetedDomainsProtection $true] [-TargetedDomainProtectionAction Quarantine] [-TargetedDomainQuarantineTag <QuarantineTagName>] [-EnableTargetedUserProtection $true] [-TargetedUserProtectionAction Quarantine] [-TargetedUserQuarantineTag <QuarantineTagName>] ...
```

**注意**:

- _Enable\*_ パラメーターは、特定の保護機能を有効にするために必要です。 _EnableMailboxIntelligence_ パラメーターと _EnableSpoofIntelligence_ パラメーターの既定値は$trueであるため、PowerShell で新しいフィッシング対策ポリシーを作成するときにこれらのパラメーターを使用する必要はありません。 他のすべての _Enable\*_ パラメーターには値$true を設定して、対応する _\*Action_ パラメーターで "Quarantine" の値を設定し、検疫ポリシーを割り当てることができます。 どの _*\Action_ パラメーターも規定で "Quarantine" の値に設定されていません。

  既存のフィッシング対策ポリシーで重要なパラメーター値を確認するには、次のコマンドを実行します:

  ```powershell
  Get-AntiPhishPolicy | Format-List Name,Enable*Intelligence,Enable*Protection,*Action,*QuarantineTag
  ```

  Standard と Strict の既定のアクション値と推奨されるアクション値については、「[EOP フィッシング対策ポリシー設定](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)」と「[Microsoft Defender for Office 365 のフィッシング対策ポリシーの偽装設定](recommended-settings-for-eop-and-office365.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)」を参照してください。

- フィッシング対策ポリシーを作成する際に、フィッシング対策アクションに対応する検疫ポリシー パラメーターがない場合は、その判定の[既定の検疫ポリシー](#step-2-assign-a-quarantine-policy-to-supported-features)が使用されることを意味します。

  特定の判定に対して検疫済みメッセージの既定のエンド ユーザー機能を変更する場合にのみ、既定の検疫ポリシーをカスタム検疫ポリシーに置き換える必要があります。

- PowerShell の新しいフィッシング対策ポリシーでは、 **New-AntiPhishPolicy** コマンドレットを使用したフィッシング対策ポリシー (設定) と **New-AntiPhishRule** コマンドレットを使用した排他的なフィッシング ルール (受信者フィルター) が必要です。 手順については、次のトピックを参照してください:
  - [PowerShell を使用して EOP でフィッシング対策ポリシーを構成する](configure-anti-phishing-policies-eop.md#use-exchange-online-powershell-to-configure-anti-phishing-policies)
  - [Exchange Online PowerShell を使用してフィッシング対策ポリシーを構成する](configure-mdo-anti-phishing-policies.md#use-exchange-online-powershell-to-configure-anti-phishing-policies)

この例では、以下の設定で、Research Department という名前の新しい安全なフィッシング対策ルールを作成します:

- すべてのスパム フィルターの判定のアクションは "Quarantine" に設定されます。
- [**アクセスなし**] のアクセス許可を割り当てる NoAccess という名前のカスタム検疫ポリシーは、既定で、[**アクセスなし**] のアクセス許可がまだ割り当てられていない既定の検疫ポリシーに置き換えられます。

```powershell
New-AntiPhishPolicy -Name "Research Department" -AuthenticationFailAction Quarantine -SpoofQuarantineTag NoAccess -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -MailboxIntelligenceQuarantineTag NoAccess -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainProtectionAction Quarantine -TargetedDomainQuarantineTag NoAccess -EnableTargetedUserProtection $true -TargetedUserProtectionAction Quarantine -TargetedUserQuarantineTag NoAccess
```

構文とパラメーターの詳細については、「[New-MalwareFilterRule](/powershell/module/exchange/new-antiphishpolicy)」を参照してください。

この例では、Human Resource という名前の既存のフィッシング対策ポリシーを変更します。 ユーザー偽装とドメイン偽装に対する保護によって検出されたメッセージのアクションは "Quarantine" に設定され、NoAccess という名前のカスタム検疫ポリシーが割り当てられます。

```powershell
Set-AntiPhishPolicy -Identity "Human Resources" -EnableTargetedDomainsProtection $true -TargetedDomainProtectionAction Quarantine -TargetedDomainQuarantineTag NoAccess -EnableTargetedUserProtection $true -TargetedUserProtectionAction Quarantine -TargetedUserQuarantineTag NoAccess
```

構文とパラメーターの詳細については、「[Set-AntiPhishPolicy](/powershell/module/exchange/set-antiphishpolicy)」を参照してください。

### <a name="anti-malware-policies"></a>マルウェア対策ポリシー

1. [Microsoft 365 Defender ポータル](https://security.microsoft.com)で、[**ポリシー**] セクションの [**メールとコラボレーション**] \> [**ポリシーとルール**] \> [**脅威ポリシー**] \> [**マルウェア対策**] に移動します。

   [**マルウェア対策ポリシー**] ページに直接移動するには、<https://security.microsoft.com/antimalwarev2> を使用します。

2. [**マルウェア対策**] ページで、次のいずれかの手順を実行します:
   - 既存のマルウェア対策ポリシーを見つけて選択する。
   - 新しいマルウェア対策ポリシーを作成する。

3. 次のいずれかの手順を実行します。
   - **既存のものを編集する**: ポリシーの名前をクリックしてポリシーを選択します。 表示された詳細のポップアップで、**[保護設定]** セクションを選択し、**[保護設定の編集]** をクリックします。
   - **新規作成**: 新しいポリシー ウィザードで、[**アクション**] ページに移動します。

4. [**保護の設定**] ページで、[**検疫ポリシー**] ボックスで検疫ポリシーを選択します。

   **注**: 新しいポリシーを作成する際に、**検疫ポリシー** 値が空なのは、既定の検疫ポリシーが使用されていることを示します。 後でポリシーを編集すると、前の表で説明したように、空の値が実際の既定の検疫ポリシー名に置き換えられます。

#### <a name="anti-malware-policies-in-powershell"></a>PowerShell のマルウェア対策ポリシー

PowerShell を使用してマルウェア対策ポリシーで検疫ポリシーを割り当てる場合は、Exchange Online PowerShell または Exchange Online Protection PowerShell に接続し、次の構文を使用します:

```powershell
<New-AntiMalwarePolicy -Name "<Unique name>" | Set-AntiMalwarePolicy -Identity "<Policy name>"> [-QuarantineTag <QuarantineTagName>]
```

**注意**:

- 新しいマルウェア対策ポリシーを作成するときに、QuarantineTag パラメーターを使用せずに新しいマルウェア対策ポリシーを作成すると、マルウェア検出の既定の検疫ポリシーが (AdminOnlyAccessPolicy) が使用されます。

  マルウェアとして検疫されたメッセージの既定のエンド ユーザー機能を変更する場合にのみ、既定の検疫ポリシーをカスタム検疫ポリシーに置き換える必要があります。

  既存のフィッシング対策ポリシーで重要なパラメーター値を確認するには、次のコマンドを実行します:

  ```powershell
  Get-MalwareFilterPolicy | Format-Table Name,QuarantineTag
  ```

- PowerShell の新しいマルウェア対策ポリシーでは、**New-MalwareFilterPolicy** コマンドレットを使用したマルウェア フィルター ポリシー (設定) と、**New-MalwareFilterRule** コマンドレットを使用した排他的マルウェア フィルター規則 (受信者フィルター) が必要です。 手順については、「[Exchange Online PowerShell またはスタンドアロン EOP PowerShell を使用してマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-malware-policies)」を参照してください。

この例では、検疫されたメッセージに [**アクセスなし**] のアクセス許可を割り当てる NoAccess という名前のカスタム検疫ポリシーを使う Research Department という名前のマルウェア フィルター ポリシーを作成します。

```powershell
New-MalwareFilterPolicy -Name "Research Department" -QuarantineTag NoAccess
```

構文とパラメーターの詳細については、「[New-MalwareFilterPolicy](/powershell/module/exchange/new-malwarefilterpolicy)」を参照してください。

この例では、検疫されたメッセージに [**アクセスなし**] というアクセス許可を割り当てる NoAccess という名前のカスタム検疫ポリシーを割り当てることによって Human Resources という名前の既存のマルウェア フィルター ポリシーを変更します。

```powershell
New-MalwareFilterPolicy -Identity "Human Resources" -QuarantineTag NoAccess
```

構文とパラメーターの詳細については、「[Set-MalwareFilterPolicy](/powershell/module/exchange/set-malwarefilterpolicy)」を参照してください。

### <a name="safe-attachments-policies-in-defender-for-office-365"></a>Defender for Office 365 の安全な添付ファイル ポリシーを設定する

1. [Microsoft 365 Defender ポータル](https://security.microsoft.com)で、[**ポリシー**] セクションの [**メールとコラボレーション**] \> [**ポリシーとルール**] \> [**脅威ポリシー**] \> [**安全な添付ファイル**] に移動します。

   **[安全な添付ファイル]** ページに直接移動するには、<https://security.microsoft.com/safeattachmentv2> を使用します。

2. **[安全な添付ファイル]** ページで、次のいずれかの手順を実行します:
   - 既存のセーフ添付ファイル ポリシーを見つけて選択する。
   - 新しいセーフ添付ファイル ポリシーを作成する。

3. 次のいずれかの手順を実行します。
   - **既存のものを編集する**: ポリシーの名前をクリックしてポリシーを選択します。 ポリシーの詳細ポップアップで、[**設定**] セクションに移動し、[**設定の編集]** をクリックします。
   - **新規作成**: 新しいポリシー ウィザードで、[**設定**] ページに移動します。

4. [**設定**] ページで、以下の手順を実行します:
   1. **安全な添付ファイルの不明なマルウェア対応**: [**ブロック**]、[**置換**]、または [**動的配信**] を選択します。
   2. [**検疫ポリシー**] ボックスで、検疫ポリシーを選択します。

   **注**: 新しいポリシーを作成する際に、[**検疫ポリシー**] の値が空なのは、既定の検疫ポリシーが使用されていることを示します。 後でポリシーを編集すると、前の表で説明したように、空の値が実際の既定の検疫ポリシー名に置き換えられます。

安全な添付ファイル ポリシーの作成と変更に関する詳細な手順は、「[Microsoft Defender for Office 365 で安全な添付ファイル ポリシーを設定する](set-up-safe-attachments-policies.md)」で説明しています。

#### <a name="safe-attachments-policies-in-powershell"></a>PowerShell の安全な添付ファイル ポリシー

PowerShell を使用して安全な添付ファイル ポリシーで検疫ポリシーを割り当てる場合は、Exchange Online PowerShell または Exchange Online Protection PowerShell に接続し、次の構文を使用します:

```powershell
<New-SafeAttachmentPolicy -Name "<Unique name>" | Set-SafeAttachmentPolicy -Identity "<Policy name>"> -Enable $true -Action <Block | Replace | DynamicDelivery> [-QuarantineTag <QuarantineTagName>]
```

**注意**:

- _Action_ パラメーターの値 [ブロック]、[置換]、または [DynamicDelivery] の順に選択すると、メッセージが検疫される可能性があります ([許可] はメッセージを検疫しません)。 _Action_ パラメーターの値は、_Enable_ パラメーターの値が `$true` の場合にのみ意味があります。

- QuarantineTag パラメーターを使用せずに新しい安全な添付ファイル ポリシーを作成すると、メール内の安全な添付ファイル検出の既定の検疫ポリシー (AdminOnlyAccessPolicy) が使用されます。

  既定の検疫ポリシーをカスタム検疫ポリシーに置き換える必要があるのは、安全な添付ファイル ポリシーによって検疫されるメール メッセージの既定のエンド ユーザー機能を変更する場合のみです。

  重要なパラメーター値を確認するには、次のコマンドを実行します:

  ```powershell
  Get-SafeAttachmentPolicy | Format-List Name,Enable,Action,QuarantineTag
  ```

- PowerShell の新しい安全な添付ファイル ポリシーには、**New-SafeAttachmentPolicy** コマンドレットを使用した安全な添付ファイル ポリシー (設定) と **New-SafeAttachmentRule** を使用した排他的安全な添付ファイルルール (受信者フィルター) が必要です。 詳細については、この記事で後述する「[Exchange Online PowerShell または スタンドアロン EOP PowerShell を使用して安全な添付ファイル ポリシーを構成する](set-up-safe-attachments-policies.md#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies)」セクションを参照してください。

この例では、検出したメッセージをブロックして、検疫されたメッセージに [**アクセスなし**] というアクセス許可を割り当てる NoAccess という名前のカスタム検疫ポリシーを使う Research Department という名前の安全な添付ファイル ポリシーを作成します。

```powershell
New-SafeAttachmentPolicy -Name "Research Department" -Enable $true -Action Block -QuarantineTag NoAccess
```

構文とパラメーターの詳細については、「[New-MalwareFilterPolicy](/powershell/module/exchange/new-malwarefilterpolicy)」を参照してください。

この例では、[**アクセスなし**] というアクセス許可を割り当てる NoAccess という名前のカスタム検疫ポリシーを割り当てることによって Human Resources という名前の既存の安全な添付ファイル ポリシーを変更します。

```powershell
Set-SafeAttachmentPolicy -Identity "Human Resources" -QuarantineTag NoAccess
```

構文とパラメーターの詳細については、「[Set-MalwareFilterPolicy](/powershell/module/exchange/set-malwarefilterpolicy)」を参照してください。

## <a name="configure-global-quarantine-notification-settings-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルでグローバル検疫通知設定を構成する

検疫ポリシーのグローバル設定を使用すると、検疫ポリシーで検疫通知が有効になっている場合に、検疫済みメッセージの受信者に送信される検疫通知をカスタマイズできます。 これらの通知の詳細については、「[検疫通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)」を参照してください。

1. Microsoft 365 Defender ポータルの [**ルール**] セクションで、[**メールとコラボレーション**] \> [**ポリシーとルール**] \> [**脅威ポリシー**] \> [**検疫ポリシー**] に移動します。 または、[ **検疫ポリシー]** ページに直接移動するには、 <https://security.microsoft.com/quarantinePolicies>.

2. [ **検疫ポリシー] ページで** 、[ **グローバル設定**] を選択します。

3. 開いた **検疫通知の設定** ポップアップで、次の設定を構成します。

   - 受信者の言語に基づいて検疫通知をカスタマイズします。

     - 次のスクリーンショットに示すように、検疫通知で使用される送信者の **表示名** 。

       :::image type="content" source="../../media/quarantine-tags-esn-customization-display-name.png" alt-text="検疫通知のカスタマイズされた送信者の表示名。" lightbox="../../media/quarantine-tags-esn-customization-display-name.png":::

     - 検疫通知の下部に追加される **免責事項** テキスト。 ローカライズされたテキスト **である組織の免責事項は** 、常に最初に含まれ、次のスクリーンショットに示すように指定したテキストが続きます。

       :::image type="content" source="../../media/quarantine-tags-esn-customization-disclaimer.png" alt-text="検疫通知の下部にあるカスタム免責事項。" lightbox="../../media/quarantine-tags-esn-customization-disclaimer.png":::

     - **表示名** と **免責事項** の値の言語識別子。 検疫通知は、受信者の言語設定に基づいて既にローカライズされています。 **表示名** と **免責事項** の値は、受信者の言語に適用される検疫通知で使用されます。

       [**表示名**] ボックスと [**免責事項**] ボックスに値を入力する _前に_、[**言語の選択**] ボックスで言語を選択します。 **[言語の選択**] ボックスの値を変更すると、[**表示名**] ボックスと [**免責事項**] ボックスの値が空になります。

     受信者の言語に基づいて検疫通知をカスタマイズするには、次の手順に従います。

     1. [言語の選択] ボックスから **言語を選択** します。 既定値は **既定** です。これは、Microsoft 365 組織の既定の言語を意味します。 詳細については、「 [Microsoft 365 の言語と地域の設定を設定する方法」を](/office365/troubleshoot/access-management/set-language-and-region)参照してください。
     2. **[表示名]** と [**免責事項]** に値を入力します。 値は言語ごとに一意である必要があります。 複数の言語で **表示名** または **免責事項** の値を再利用しようとすると、[ **保存**] をクリックするとエラーが発生します。
     3. [**追加**] ボタンをクリックします。
     4. 前の手順を繰り返して、受信者の言語に基づいてカスタマイズされた検疫通知を最大 3 つ作成します。 ラベルのないボックスには、構成した言語が表示されます。

        :::image type="content" source="../../media/quarantine-tags-esn-customization-selected-languages.png" alt-text="検疫ポリシーのグローバル検疫通知設定で選択された言語。" lightbox="../../media/quarantine-tags-esn-customization-selected-languages.png":::

   - **会社のロゴを使用**: 検疫通知の上部で使用される既定の Microsoft ロゴを置き換えるには、このオプションを選択します。 この手順を行う前に、 [組織の Microsoft 365 テーマをカスタマイズ](../../admin/setup/customize-your-organization-theme.md) してカスタム ロゴをアップロードする手順に従う必要があります。 アップロードされたカスタム ロゴ ファイルの代わりに URL を指すカスタム ロゴが組織にある場合、このオプションはサポートされません。 

     次のスクリーンショットは、検疫通知のカスタム ロゴを示しています:

     :::image type="content" source="../../media/quarantine-tags-esn-customization-logo.png" alt-text="検疫通知のカスタム ロゴ" lightbox="../../media/quarantine-tags-esn-customization-logo.png":::

   - **エンド ユーザーのスパム通知を毎 (日) 送信する**: 検疫通知の頻度を選択します。 既定値は 3 日ですが、1 日から 15 日を選択できます。

4. 完了したら、**[保存]** をクリックします。

   :::image type="content" source="../../media/mdo-quarantine-policy-quarantine-notification-settings.png" alt-text="Microsoft 365 Defender ポータルの検疫通知設定ポップアップ。" lightbox="../../media/mdo-quarantine-policy-quarantine-notification-settings.png":::

## <a name="view-quarantine-policies-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルで検疫ポリシーを表示する

1. Microsoft 365 Defender ポータルの [**ルール**] セクションで、[**メールとコラボレーション**] \> [**ポリシーとルール**] \> [**脅威ポリシー**] \> [**検疫ポリシー**] に移動します。 または、[ **検疫ポリシー]** ページに直接移動するには、 <https://security.microsoft.com/quarantinePolicies>.

2. **[検疫ポリシー]** ページには、**名前** と最終更新日によるポリシーの一覧 **が** 表示されます。

3. 組み込みまたはカスタムの検疫ポリシーの設定を表示するには、名前をクリックして、一覧から検疫ポリシーを選択します。

4. グローバル設定を表示するには、[**グローバル設定**] をクリックします。

### <a name="view-quarantine-policies-in-powershell"></a>PowerShell で検疫ポリシーを表示する

PowerShell を使用して検疫ポリシーを表示する場合は、次のいずれかの手順を実行します:

- 組織内のすべての組み込みまたはカスタムのポリシーを表示するには、以下のコマンドを実行します:

  ```powershell
  Get-QuarantinePolicy | Format-Table Name
  ```

- 組み込みまたはカスタムの検疫ポリシーの設定を表示するには、\<QuarantinePolicyName\> を検疫ポリシーの名前に置き換えて、次のコマンドを実行します:

  ```powershell
  Get-QuarantinePolicy -Identity "<QuarantinePolicyName>"
  ```

- 検疫通知のグローバル設定を表示するには、次のコマンドを実行します:

  ```powershell
  Get-QuarantinePolicy -QuarantinePolicyType GlobalQuarantinePolicy
  ```

構文とパラメーターの詳細については、「[Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy)」を参照してください。

## <a name="modify-quarantine-policies-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルで検疫ポリシーを変更する

AdminOnlyAccessPolicy または DefaultFullAccessPolicy という名前の組み込みの検疫ポリシーは変更できません。 NotificationEnabledPolicy という名前の組み込みポリシー ([存在する場合](#full-access-permissions-and-quarantine-notifications)) とカスタム検疫ポリシーは変更できます。

1. Microsoft 365 Defender ポータルの [**ルール**] セクションで、[**メールとコラボレーション**] \> [**ポリシーとルール**] \> [**脅威ポリシー**] \> [**検疫ポリシー**] に移動します。 または、[ **検疫ポリシー]** ページに直接移動するには、 <https://security.microsoft.com/quarantinePolicies>.

2. [**検疫ポリシー**] ページで、名前をクリックしてポリシーを選択します。

3. ポリシーを選択したら、[![ポリシーの編集](../../media/m365-cc-sc-edit-icon.png)] アイコンをクリックします。 表示される [**ポリシーの編集**] アイコン。

4. 開く **ポリシーの編集** ウィザードは、この記事の「[Microsoft 365 Defender ポータルの検疫ポリシーの作成](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal)」セクションで説明した **新しいポリシー** ウィザードと実質的に同じです。

   主な違いは、既存のポリシーの名前を変更できない点です。

5. ポリシーの変更が完了したら、[**概要**] ページに移動し、[**送信**] をクリックします。

### <a name="modify-quarantine-policies-in-powershell"></a>PowerShell で検疫ポリシーを変更する

PowerShell を使用してカスタム検疫ポリシーを変更する場合は、次の構文を \<QuarantinePolicyName\> を検疫ポリシーの名前に置き換えて使用します:

```powershell
Set-QuarantinePolicy -Identity "<QuarantinePolicyName>" [Settings]
```

使用可能な設定は、この記事の前半で説明した検疫ポリシーを作成する場合と同じです。

構文とパラメーターの詳細については、「[Set-QuarantinePolicy](/powershell/module/exchange/set-quarantinepolicy)」を参照してください。

## <a name="remove-quarantine-policies-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルで検疫ポリシーを削除する

**注意**:

- AdminOnlyAccessPolicy または DefaultFullAccessPolicy という名前の組み込みの検疫ポリシーは削除することはできません。 NotificationEnabledPolicy という名前の組み込みポリシー ([存在する場合](#full-access-permissions-and-quarantine-notifications)) とカスタム検疫ポリシーは削除できます。
- 検疫ポリシーを削除する前に、それが使用されていないことを確認します。 たとえば、PowerShell で次のコマンドを実行します:

  ```powershell
  Write-Output -InputObject "Anti-spam policies","----------------------";Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag; Write-Output -InputObject "Anti-phishing policies","----------------------";Get-AntiPhishPolicy | Format-List Name,*QuarantineTag; Write-Output -InputObject "Anti-malware policies","----------------------";Get-MalwareFilterPolicy | Format-List Name,QuarantineTag; Write-Output -InputObject "Safe Attachments policies","---------------------------";Get-SafeAttachmentPolicy | Format-List Name,QuarantineTag
  ```

  検疫ポリシーが使用されている場合は、 削除する前に[割り当てられた検疫ポリシー置き換え](#step-2-assign-a-quarantine-policy-to-supported-features)ます。

1. Microsoft 365 Defender ポータルの [**ルール**] セクションで、[**メールとコラボレーション**] \> [**ポリシーとルール**] \> [**脅威ポリシー**] \> [**検疫ポリシー**] に移動します。 または、[ **検疫ポリシー]** ページに直接移動するには、 <https://security.microsoft.com/quarantinePolicies>.

2. [ **検疫ポリシー** ] ページで、名前をクリックして削除するカスタム検疫ポリシーを選択します。

3. ポリシーを選択したら、[![ポリシーの削除](../../media/m365-cc-sc-delete-icon.png)] アイコンを クリックします。 表示される [**ポリシーの削除**] アイコン。

4. 表示される確認ダイアログで [**ポリシーの削除**] をクリックします。

### <a name="remove-quarantine-policies-in-powershell"></a>PowerShell で検疫ポリシーを削除する

PowerShell を使用してカスタム検疫ポリシーを削除する場合は、\<QuarantinePolicyName\> を検疫ポリシーの名前に置き換えて、次のコマンドを実行します:

```powershell
Remove-QuarantinePolicy -Identity "<QuarantinePolicyName>"
```

構文とパラメーターの詳細については、「[Remove-QuarantinePolicy](/powershell/module/exchange/remove-quarantinepolicy)」を参照してください。

## <a name="system-alerts-for-quarantine-release-requests"></a>検疫解放要求のシステム アラート

既定では、"**検疫されたメッセージの解放を要求されたユーザー**" という名前の既定のアラート ポリシーは、情報アラートを自動的に生成し、ユーザーが検疫されたメッセージの解放を要求するたびに、次のロール グループのメンバーに通知メッセージを送信します:

- 検疫管理者
- セキュリティ管理者
- 組織の管理 (グローバル管理者)

管理者は、メール通知の受信者をカスタマイズしたり、その他のオプションのカスタム アラート ポリシーを作成したりできます。

アラート ポリシーの詳細については、「[Alert policies in Microsoft 365 (Microsoft 365 でのアラート ポリシー)](../../compliance/alert-policies.md)」を参照してください。

## <a name="quarantine-policy-permission-details"></a>検疫ポリシーのアクセス許可の詳細

次のセクションでは、検疫済みメッセージの詳細と検疫通知における、事前設定されたアクセス許可グループと個々のアクセス許可の効果について説明します。

### <a name="preset-permissions-groups"></a>事前設定されたアクセス許可グループ

事前設定されたアクセス許可グループに含まれる個々のアクセス許可は、この記事の冒頭の表に記載されています。

#### <a name="no-access"></a>アクセスなし

検疫ポリシーで [**アクセスなし**] (管理者のみアクセス) のアクセス許可が割り当てられている場合、ユーザーは検疫されたメッセージを表示できません。

- **検疫済みメッセージの詳細**: エンド ユーザー ビューに表示されるメッセージはありません。
- **検疫通知**: これらのメッセージに対する通知は送信されません。

#### <a name="limited-access"></a>制限付きアクセス

検疫ポリシーで [**制限付きアクセス**] のアクセス許可が割り当てられている場合、ユーザーは次の機能を利用できます:

- **検疫済みメッセージの詳細**: 次のボタンを使用できます:
  - **解放の要求**
  - **メッセージ ヘッダーを表示する**
  - **メッセージのプレビュー**
  - **検疫から削除**
  - **差出人をブロックする**

  :::image type="content" source="../../media/quarantine-tags-quarantined-message-details-limited-access.png" alt-text="検疫ポリシーでユーザーに制限付きアクセス許可が付与されている場合の、検疫済みメッセージの詳細で使用可能なボタン" lightbox="../../media/quarantine-tags-quarantined-message-details-limited-access.png":::

- **検疫通知**: 次のボタンを使用できます:
  - **差出人をブロックする**
  - **解放の要求**
  - **確認**

  :::image type="content" source="../../media/quarantine-tags-esn-limited-access.png" alt-text="検疫ポリシーによりユーザーに制限付きアクセス許可が付与されている場合に検疫通知で使用可能なボタン" lightbox="../../media/quarantine-tags-esn-limited-access.png":::

#### <a name="full-access"></a>フル アクセス

検疫ポリシーで [**フル アクセス**] 許可 (使用可能なすべてのアクセス許可) が割り当てられている場合、ユーザーは次の機能を利用できます:

- **検疫済みメッセージの詳細**: 次のボタンを使用できます:
  - **解放メッセージ**
  - **メッセージ ヘッダーを表示する**
  - **メッセージのプレビュー**
  - **検疫から削除**
  - **差出人をブロックする**

  :::image type="content" source="../../media/quarantine-tags-quarantined-message-details-full-access.png" alt-text="検疫ポリシーでユーザーにフル アクセス許可が付与されている場合に検疫済みメッセージの詳細で使用可能なボタン" lightbox="../../media/quarantine-tags-quarantined-message-details-full-access.png":::

- **検疫通知**: 次のボタンを使用できます:
  - **差出人をブロックする**
  - **Release**
  - **確認**

  :::image type="content" source="../../media/quarantine-tags-esn-full-access.png" alt-text="検疫ポリシーでユーザーにフル アクセス許可が付与されている場合に検疫通知で使用可能なボタン" lightbox="../../media/quarantine-tags-esn-full-access.png":::

> [!NOTE]
> 前述のように、検疫ポリシーに **フル アクセス** 許可グループが割り当てられている場合でも、検疫通知は DefaultFullAccessPolicy という名前の既定の検疫ポリシーで無効になります。 検疫通知は、作成したカスタム検疫ポリシーまたは NotificationEnabledPolicy という名前の既定の検疫アクセス ポリシーでのみ[使用できます (そのポリシーが組織で使用可能な場合](#full-access-permissions-and-quarantine-notifications))。

### <a name="individual-permissions"></a>個々のアクセス許可

#### <a name="block-sender-permission"></a>送信者ブロックのアクセス許可

[**送信者のブロック**] アクセス許可 (_PermissionToBlockSender_) は、検疫済みのメッセージ送信者をユーザーが受信拒否リストに簡単に追加できるボタンの使用を制御します。

- **検疫済みメッセージの詳細**:
  - [**送信者ブロック**] のアクセス許可が有効: [**送信者のブロック**] ボタンが使用できます。
  - [**送信者ブロック**] のアクセス許可が無効: [**送信者のブロック**] ボタンは使用できません。

- **検疫通知**:
  - [**送信者ブロック**] のアクセス許可が有効: [**送信者のブロック**] ボタンが使用できます。
  - [**送信者ブロック**] のアクセス許可が無効: [**送信者のブロック**] ボタンは使用できません。

受信拒否リストの詳細については、「[ユーザーからのメッセージをブロックする](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667)」と「[PowerShell Exchange Online を使用してメールボックスのセーフリスト コレクションを構成する](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)」を参照してください。

#### <a name="delete-permission"></a>削除のアクセス許可

[**削除**] のアクセス許可 (_PermissionToDelete_) は、ユーザーがメッセージ (ユーザーが受信者であるメッセージ) を検疫から削除できる機能を制御します。

- **検疫済みメッセージの詳細**:
  - [**削除**] のアクセス許可が有効: [**検疫から削除**] ボタンが使用できます。
  - [**削除**] のアクセス許可が無効: [**検疫から削除**] ボタンは使用できません。

- **検疫通知**: 効果はありません。

#### <a name="preview-permission"></a>プレビューのアクセス許可

[**プレビュー**] のアクセス許可 (_PermissionToPreview_) は、ユーザーが検疫でメッセージをプレビューできる機能を制御します。

- **検疫済みメッセージの詳細**:
  - **プレビュー** アクセス許可が有効: [**メッセージのプレビュー**] ボタンが使用できます。
  - **プレビュー** アクセス許可が無効: [**メッセージのプレビュー**] ボタンは使用できません。

- **検疫通知**: 効果はありません。

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a>検疫からのメッセージ解放を要求するアクセス許可を受信者に許可する

> [!NOTE]
> このアクセス許可は、マルウェア対策ポリシーまたはスパム対策ポリシーの高信頼フィッシング判定では受け入れられません。 ユーザーは、独自のマルウェアや信頼度の高いフィッシング メッセージを検疫から解放できません。 [受信者を許可する] を使用 [して、検疫アクセス許可のアクセス許可から解放するメッセージを要求](#allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission) できます。

**検疫からのメッセージ解放を受信者が要求する** アクセス許可 (_PermissionToRelease_) は、管理者の承認なしに、ユーザーが検疫済みメッセージを直接解放する機能を制御します。

- **検疫済みメッセージの詳細**:
  - アクセス許可が有効: [**メッセージの解放**] ボタンが使用できます。
  - アクセス許可が無効: [**メッセージの解放**] ボタンは使用できません。

- **検疫通知**:
  - アクセス許可が有効: [**解放**] ボタンが使用できます。
  - アクセス許可が無効: [**解放**] ボタンは使用できません。

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a>メッセージの検疫からの解放を要求するアクセス許可を受信者に許可する

**受信者がメッセージの検疫からの解放を要求する** アクセス許可 (_PermissionToRequestRelease_) は、検疫されたメッセージの解放を _要求_ するユーザーの機能を制御します。 メッセージは、管理者が要求を承認して初めて解放されます。

- **検疫済みメッセージの詳細**:
  - アクセス許可が有効: [**解放の要求**] ボタンを使用できます。
  - アクセス許可が無効: [**解放の要求**] ボタンは使用できません。

- **検疫通知**:
  - アクセス許可が有効: [**解放の要求**] ボタンを使用できます。
  - アクセス許可が無効: [**解放の要求**] ボタンは使用できません。
