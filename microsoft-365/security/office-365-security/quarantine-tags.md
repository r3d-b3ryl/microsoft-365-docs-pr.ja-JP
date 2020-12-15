---
title: 検疫タグ
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: 管理者は、検疫タグを使用して、ユーザーが検疫済みメッセージに対して実行できる操作を制御する方法について学習できます。
ms.openlocfilehash: 167f147d7c74b78b1a1661b5444625fbf1cf3d41
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683069"
---
# <a name="quarantine-tags"></a>検疫タグ

> [!NOTE]
> この記事で説明する機能は現在プレビュー中であり、すべてのユーザーが利用できる機能ではありません。また、変更される可能性があります。

Exchange Online Protection (EOP) の検疫タグを使用すると、管理者は、メッセージが検疫に到着した方法に基づいて、ユーザーが検疫済みメッセージに対して実行できる操作を制御できます。

EOP は、従来、検疫内のメッセージとエンド ユーザーのスパム通知[](find-and-release-quarantined-messages-as-a-user.md)で、特定のレベルの対話機能を許可または[防止しました](use-spam-notifications-to-release-and-report-quarantined-messages.md)。 たとえば、エンドユーザーはスパム対策フィルターによって検疫されたメッセージをスパムまたはバルクとして表示および解放できますが、信頼度の高いフィッシングとして検疫されたメッセージを表示または解放したりは行えなくなります。

サポート [されている](#step-2-assign-a-quarantine-tag-to-supported-features)保護機能の場合、検疫タグは、エンド ユーザーのスパム通知メッセージおよび検疫済みメッセージ (ユーザーが受信者であるメッセージ) でユーザーが実行できる操作を指定します。 既定の検疫タグは、エンドユーザーに対して検疫済みメッセージの履歴機能を適用するために自動的に割り当てられます。 または、カスタム検疫タグを作成して割り当て、エンド ユーザーが検疫済みメッセージに対して特定の操作を実行する許可または防止を行うことができます。

個々のアクセス許可は、次の事前設定されたアクセス許可グループに結合されます。

- アクセスなし
- 制限付きアクセス
- フル アクセス

使用可能な個々のアクセス許可と、既定のアクセス許可グループに含まれるもの、または含まれていないものについて、次の表で説明します。

|アクセス許可|アクセスなし|制限付きアクセス|フル アクセス|
|---|:---:|:---:|:---:|
|**送信者を許可** する (_PermissionToAllowSender_)|||![チェック マーク](../../media/checkmark.png)|
|**送信者をブロック** する (_PermissionToBlockSender_)||![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|
|**Delete** (_PermissionToDelete_)||![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|
|**Preview** (_PermissionToPreview_)||![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|
|**受信者が検疫からメッセージを解放する** (_PermissionToRelease_)|||![チェック マーク](../../media/checkmark.png)|
|**受信者に検疫からのメッセージの解放を要求する** (_PermissionToRequestRelease_)||![チェック マーク](../../media/checkmark.png)||
|

既定のアクセス許可グループの既定のアクセス許可が気に入らない場合は、カスタム検疫タグを作成または変更するときにカスタムアクセス許可を使用できます。 各アクセス許可の機能の詳細については、この記事の後半の「 [検疫タグのアクセス許可の](#quarantine-tag-permission-details) 詳細」セクションを参照してください。

検疫タグは、セキュリティ & コンプライアンス センターまたは PowerShell で作成して割り当てる必要があります (Exchange Online メールボックスを使用する Microsoft 365 組織向け Exchange Online PowerShell、Exchange Online メールボックスのない EOP 組織のスタンドアロン EOP PowerShell)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [検疫タグ] ページに **直接移動するには** 、開きます <https://protection.office.com/quarantineTags> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- 検疫タグを表示、作成、変更、または削除するには、セキュリティ/コンプライアンス センターの組織の管理またはセキュリティ管理者の役割の[メンバー&必要があります](permissions-in-the-security-and-compliance-center.md)。

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a>手順 1: セキュリティ/コンプライアンス センターで検疫&作成する

1. セキュリティ/コンプライアンス センター&、脅威管理ポリシーに **移動し**、検疫 \> タグを **選択します**。

2. [検疫タグ **] ページで** 、[カスタム タグの **追加] を選択します**。

3. 新 **しいタグ ウィザード** が開きます。 [タグ **名] ページ** で、[タグ名] フィールドに一意の名前 **を入力** します。 今後の手順では、名前でタグを識別して選択する必要があります。 完了したら、**[次へ]** をクリックします。

4. [受信者 **メッセージ アクセス] ページ** で、次のいずれかの値を選択します。
   - **アクセスなし**
   - **制限付きアクセス**
   - **フル アクセス**

   これらのアクセス許可グループに含まれる個々のアクセス許可については、この記事で前述しました。

   カスタムアクセス許可を指定するには、[特定のアクセス **許可を設定する (詳細)** を選択し、次の設定を構成します。

     - **[リリースアクションの基本設定**] を選択します。次のいずれかの値を選択します。
       - **リリース操作なし**: これは既定値です。
       - **受信者による検疫からのメッセージの解放を許可する**
       - **受信者が検疫から解放されるメッセージを要求する**

     - **検疫済みメッセージに対して** 受信者が実行できるその他のアクションを選択する: 次の値の一部、すべて、またはなしを選択します。
       - **削除**
       - **プレビュー**
       - **送信者を許可する**
       - **送信者をブロックする**

   これらのアクセス許可とその影響が検疫済みメッセージおよびエンド ユーザーのスパム通知に及ぼす影響については、この記事で後述する「検疫 [タグ](#quarantine-tag-permission-details) のアクセス許可の詳細」セクションで説明します。

   完了したら、**[次へ]** をクリックします。

5. 表示される **[概要]** ページで、設定を確認します。 各設定で **[編集]** をクリックして変更できます。

   完了したら、[送信] をクリック **します**。

6. 表示 **される確認** ページで [完了] をクリックします。

これで、手順 2 のセクションで説明するように、検疫タグを検疫 [機能に割り当てる準備ができました](#step-2-assign-a-quarantine-tag-to-supported-features) 。

### <a name="create-quarantine-tags-in-powershell"></a>PowerShell で検疫タグを作成する

PowerShell を使用して検疫タグを作成する場合は、Exchange Online PowerShell または Exchange Online Protection PowerShell に接続し **、New-QuarantineTag コマンドレットを使用** します。 次の 2 つの方法から選択できます。

- _EndUserQuarantinePermissionsValue パラメーターを使用_ します。
- _EndUserQuarantinePermissions パラメーターを使用_ します。

これらのメソッドについては、以下のセクションで説明します。

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a>EndUserQuarantinePermissionsValue パラメーターを使用する

_EndUserQuarantinePermissionsValue パラメーター_ を使用して検疫タグを作成するには、次の構文を使用します。

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

_EndUserQuarantinePermissionsValue_ パラメーターは、バイナリ値から変換された 10 進値を使用します。 バイナリ値は、使用可能なエンド ユーザーによる検疫のアクセス許可に特定の順序で対応します。 アクセス許可ごとに、値 1 は True、値 0 は False に等しくなります。

事前設定されたアクセス許可グループの個々のアクセス許可に必要な順序と値を次の表に示します。

****

|アクセス許可|アクセスなし|制限付きアクセス|フル アクセス|
|---|:---:|:---:|:---:|
|PermissionToAllowSender|0|0|1 |
|PermissionToBlockSender|0|1 |1 |
|PermissionToDelete|0|1 |1 |
|PermissionToDownload<sup>\*</sup>|0|0|0|
|PermissionToPreview|0|1 |1 |
|PermissionToRelease<sup>\*\*</sup>|0|0|1 |
|PermissionToRequestRelease<sup>\*\*</sup>|0|1 |0|
|PermissionToViewHeader<sup>\*</sup>|0|0|0|
|バイナリ値|00000000|01101010|11101100|
|使用する 10 進値|0|106|236|

<sup>\*</sup> 現在、この値は常に 0 です。 PermissionToViewHeader の場合、値 0 は検疫済みメッセージの詳細に [メッセージ ヘッダーの表示] ボタンを非表示にできません (このボタンは常に使用可能です)。

<sup>\*\*</sup> これらの両方の値を 1 に設定しない。 一方を 1 に設定し、もう一方を 0 に設定するか、両方を 0 に設定します。

この例では、前の表で説明したように、No アクセス許可を割り当てる新しい検疫タグ名 NoAccess を作成します。

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

制限付きアクセス許可の場合は、値 106 を使用します。 フル アクセス許可の場合は、値 236 を使用します。

カスタム アクセス許可の場合は、前の表を使用して、必要なアクセス許可に対応するバイナリ値を取得します。 2 進数の値を 10 進数の値に変換し _、EndUserQuarantinePermissionsValue パラメーターに 10 進値を使用_ します。

構文およびパラメーターの詳細については [、「New-QuarantineTag」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)。

#### <a name="use-the-enduserquarantinepermissions-parameter"></a>EndUserQuarantinePermissions パラメーターを使用する

_EndUserQuarantinePermissionsValue パラメーター_ を使用して検疫タグを作成するには、次の手順を実行します。

A. **New-QuarantinePermissions** コマンドレットを使用して、変数に検疫アクセス許可オブジェクトを格納します。

<p>

B. 変数を **New-QuarantineTag** コマンドの _EndUserQuarantinePermissions_ 値として使用します。

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a>手順 A: 検疫のアクセス許可オブジェクトを変数に格納する

次の構文を使用してください。

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

使用されていないパラメーターの既定値は次の値なので、値を設定するパラメーターのみを `$false` 使用する必要があります `$true` 。

次の例は、事前設定されたアクセス許可グループに対応するアクセス許可オブジェクトを作成する方法を示しています。

- **アクセスなし**:

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- **制限付きアクセス**:

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- **フル アクセス**:

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

設定した値を確認するには、変数名をコマンドとして実行します (たとえば、コマンドを実行します `$NoAccess` )。

カスタム アクセス許可の場合は _、PermissionToRelease_ パラメーターと _PermissionToRequestRelease_ パラメーターの両方を次に設定してください `$true` 。 一方を設定 `$true` し、もう一方を次のように設定するか `$false` 、両方を次のようにします `$false` 。

また **、Set-QuarantinePermissions** コマンドレットを使用して、作成した後で使用する前に、既存のアクセス許可オブジェクト変数を変更することもできます。

構文およびパラメーターの詳細については [、「New-QuarantinePermissions」](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) および [「Set-QuarantinePermissions」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions)。

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a>手順 B: 次のコマンドで変数をNew-QuarantineTagする

アクセス許可オブジェクトを作成して変数に格納したら、次の **New-QuarantineTag** コマンドで _EndUserQuarantinePermission_ パラメーター値の変数を使用します。

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

この例では、前の手順で説明および作成したアクセス許可オブジェクトを使用して、LimitedAccess という名前の新しい検疫 `$LimitedAccess` タグを作成します。

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

構文およびパラメーターの詳細については [、「New-QuarantineTag」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)。

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a>手順 2: サポートされている機能に検疫タグを割り当てる

メッセージ _またはファイルを_ 検疫するサポートされる保護機能 (自動的に、または構成可能なアクションとして) では、使用可能な検疫アクションに検疫タグを割り当てることもできます。 次の表に、メッセージを検疫する機能と検疫タグの可用性について説明します。

****

|機能|サポートされている検疫タグ|使用される既定の検疫タグ|
|---|:---:|---|
|[スパム対策ポリシー](configure-your-spam-filter-policies.md): <ul><li>**Spam** (_SpamAction_)</li><li>**信頼度の高い** スパム (_HighConfidenceSpamAction_)</li><li>**フィッシング メール** (_PhishSpamAction_)</li><li>**信頼度の高いフィッシングメール** (_HighConfidencePhishAction_)</li><li>**バルク メール** (_BulkSpamAction_)</li></ul>|はい|<ul><li>DefaultSpamTag (フル アクセス)</li><li>DefaultHighConfSpamTag (フル アクセス)</li><li>DefaultPhishTag (フル アクセス)</li><li>DefaultHighConfPhishTag (アクセスなし)</li><li>DefaultBulkTag (フル アクセス)</li></ul>
|フィッシング対策ポリシー: <ul><li>[スプーフィング インテリジェンス保護](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</li><li>[偽装保護](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup> <ul><li>**偽装されたユーザーによって電子メールが送信される場合** (_TargetedUserProtectionAction_)</li><li>**偽装ドメイン**_(TargetedDomainProtectionAction) によって電子メールが送信される場合_</li><li>**メールボックス インテリジェンス** \>**偽装されたユーザーによって電子メールが送信** される場合 (_MailboxIntelligenceProtectionAction_)</li></ul></li></ul></ul>|いいえ|該当なし|
|[マルウェア対策ポリシー](configure-anti-malware-policies.md): 検出されたメッセージはすべて常に検疫されます。|いいえ|該当なし|
|[SharePoint、OneDrive、Microsoft Teams 用の ATP](atp-for-spo-odb-and-teams.md)|いいえ|該当なし|
|[アクションを含む](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) メール フロー ルール (トランスポート ルールとも呼ばれる): ホストされた検疫 (検疫) にメッセージ **を** 配信 _します_。|いいえ|該当なし|
|

<sup>\*</sup> 偽装保護の設定は、Microsoft Defender for Office 365 のフィッシング対策ポリシーでのみ使用できます。

既定の検疫タグによって提供されるエンド ユーザーのアクセス許可に満足している場合は、何もする必要はありません。 エンド ユーザーのスパム通知または検疫済みメッセージの詳細でエンド ユーザーの機能 (使用可能なボタン) をカスタマイズする場合は、カスタム検疫タグを割り当てできます。

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターでスパム対策ポリシーに検疫タグ&割り当てる

スパム対策ポリシーを作成および変更するための詳細な手順については [、「EOP](configure-your-spam-filter-policies.md)でスパム対策ポリシーを構成する」を参照してください。

1. セキュリティ/コンプライアンス センター&、脅威管理ポリシーに **移動し**、[スパム対策] \>  \> **を選択します**。 または、開きます <https://protection.office.com/antispam> 。

2. 既存のスパム対策ポリシーを検索して選択し、編集するか、新しいスパム対策ポリシーを作成します。

3. ポリシーの詳細のフライアウトで、[スパムと一括アクション **] セクションを展開** します。

4. 利用可能なスパム フィルターの条件のアクションに対して [検疫メッセージ] を選択した場合は、[検疫ポリシーの適用] タグ ボックスを使用して、その条件の検疫タグを選択できます。

   **注**: 新しいポリシーを作成すると、スパム フィルターの条件に対して空白の検疫タグ値が使用されます。 後でポリシーを編集すると、前の表で説明したように、空白値が実際の既定の検疫タグ名に置き換えられる。

   ![スパム対策ポリシーでの検疫タグの選択](../../media/quarantine-tags-in-anti-spam-policies.png)

5. 完了したら、**[保存]** をクリックします。

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a>PowerShell でスパム対策ポリシーで検疫タグを割り当てる

スパム対策ポリシーで検疫タグを割り当てるには、PowerShell を使用する場合は、Exchange Online PowerShell または Exchange Online Protection PowerShell に接続し、次の構文を使用します。

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

**注**:

- _HighConfidencePhishAction_ パラメーターの既定値は Quarantine なので、新しいスパム対策ポリシーで信頼度の高いフィッシング検出の検疫アクションを設定する必要はありません。 新規または既存のスパム対策ポリシーの他のすべてのスパム フィルターの条件では、検疫タグはアクションの値が Quarantine の場合にのみ有効です。 既存のスパム対策ポリシーのアクション値を表示するには、次のコマンドを実行します。

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  Standard および Strict の既定のアクション値と推奨されるアクション値の詳細については、「EOP スパム対策ポリシー設定」 [を参照してください](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)。

- 対応する検疫タグ パラメーターを指定しないスパム フィルターの条件は[](#step-2-assign-a-quarantine-tag-to-supported-features)、その確認の既定の検疫タグが使用されるという意味です。

  既定の検疫タグをカスタム検疫タグに置き換える必要があるのは、検疫済みメッセージの既定のエンド ユーザー機能を変更する場合のみです。

- PowerShell の新しいスパム対策ポリシーには **、New-HostedContentFilterPolicy** コマンドレットを使用するスパム フィルター ポリシー (設定) と **、New-HostedContentFilterRule** コマンドレットを使用する新しいスパム フィルター ルール (受信者フィルター) が必要です。 手順については [、「PowerShell を使用してスパム対策ポリシーを作成する」を参照してください](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)。

この例では、次の設定で Research Department という名前の新しいスパム フィルター ポリシーを作成します。

- すべてのスパム フィルターの条件に対するアクションが [検疫] に設定されます。
- アクセス許可なしを割り当てる NoAccess という名前のカスタム検疫タグは、既定でアクセス許可を割り当てない既定の検疫タグに置き換わります。 

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

構文とパラメーターの詳細については、「[New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy)」を参照してください。

この例では、Human Resources という名前の既存のスパム フィルター ポリシーを変更します。 スパム検疫の確認のアクションは [検疫] に設定され、NoAccess という名前のカスタム検疫タグが割り当てられます。

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

構文とパラメーターの詳細については、「[Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)」を参照してください。

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターでグローバル検疫通知&構成する

検疫タグのグローバル設定を使用すると、検疫されたメッセージの受信者に送信されるエンドユーザーのスパム通知をカスタマイズできます。 これらの通知の詳細については、「エンド ユーザー向け [スパム通知」を参照してください](use-spam-notifications-to-release-and-report-quarantined-messages.md)。

1. セキュリティ/コンプライアンス センター&、脅威管理ポリシーに **移動し**、検疫 \> タグを **選択します**。

2. [検疫タグ **] ページで、[** グローバル設定] **を選択します**。

3. 開く **検疫通知設定** のフライアウトで、次の設定の一部またはすべてを構成します。

   - **会社のロゴを使用** する : エンド ユーザーのスパム通知の上部で使用されている既定の Microsoft ロゴを置き換える場合は、このオプションを選択します。 これを行う前に、「組織の [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) テーマをカスタマイズする」の手順に従って、カスタム ロゴをアップロードする必要があります。

     次のスクリーンショットは、エンド ユーザーのスパム通知のカスタム ロゴを示しています。

     ![エンドユーザーのスパム通知のカスタム ロゴ](../../media/quarantine-tags-esn-customization-logo.png)

   - **[言語の** 選択]: エンドユーザーのスパム通知は、受信者の言語設定に基づいて既にローカライズされています。 表示名と免責事項の値には、異なる言語 **でカスタマイズしたテキスト** を **指定** できます。

     最初の言語ボックスから少なくとも 1 つの言語を選択し、[追加] をクリック **します**。 複数の言語を選択するには、各言語の後にある [追加 **]** をクリックします。 セクションの言語ボックスには、選択した言語すべてが表示されます。

     ![検疫タグのグローバル検疫通知設定の 2 番目の言語ボックスで選択した言語](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - **表示名**: エンドユーザーのスパム通知で使用される送信者の表示名をカスタマイズします。

     追加した言語ごとに、2 番目の言語のボックス ([X] をクリックしない) で言語を選択し、[表示名] ボックスに目的のテキスト値 **を** 入力します。

     次のスクリーンショットは、エンド ユーザーのスパム通知のカスタマイズされた表示名を示しています。

     ![エンド ユーザーのスパム通知でのカスタマイズされた送信者の表示名](../../media/quarantine-tags-esn-customization-display-name.png)

   - **免責** 事項 : エンドユーザーのスパム通知の下部にカスタム免責事項を追加します。 ローカライズされたテキスト、組織からの免責事項 **:** 常に最初に含め、その後に指定したテキストが含まれます。

     追加した言語ごとに、2 番目の言語ボックス ([X] をクリックしない) で言語を選択し、必要なテキスト値を [免責事項] ボックスに **入力** します。

     次のスクリーンショットは、エンド ユーザーのスパム通知でカスタマイズされた免責事項を示しています。

     ![エンドユーザーのスパム通知の下部にあるカスタム免責事項](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターで検疫タグ&表示する

1. セキュリティ/コンプライアンス センター&、脅威管理ポリシーに **移動し**、検疫 \> タグを **選択します**。

- 組み込みまたはカスタム検疫タグの設定を表示するには、一覧から検疫タグを選択します (チェック ボックスはオンにしない)。

- グローバル設定を表示するには、[グローバル設定] **を選択します。**

### <a name="view-quarantine-tags-in-powershell"></a>PowerShell で検疫タグを表示する

PowerShell を使用して検疫タグを表示する場合は、次の手順を実行します。

- すべての組み込みタグまたはカスタム タグの要約リストを表示するには、次のコマンドを実行します。

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- 組み込みまたはカスタム検疫タグの設定を表示するには、検疫タグの名前に置き換え、次の \<TagName\> コマンドを実行します。

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- グローバル設定を表示するには、次のコマンドを実行します。

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

構文とパラメーターの詳細については、「[Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy)」を参照してください。

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターで検疫&を削除する

**注**:

- 組み込みの検疫タグは削除できない。

- カスタム検疫タグを削除する前に、そのタグが使用されていないか確認してください。 たとえば、PowerShell で次のコマンドを実行します。

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  検疫タグが使用されている場合は、割り当てられた [検疫タグを](#step-2-assign-a-quarantine-tag-to-supported-features) 削除する前に置き換える必要があります。

1. セキュリティ/コンプライアンス センター&、脅威管理ポリシーに **移動し**、検疫 \> タグを **選択します**。

2. [検疫タグ **] ページ** で、削除するカスタム検疫タグを選択し、[削除] タグを **クリックします**。

3. 表示 **される確認ダイアログ** で [タグの削除] をクリックします。

### <a name="remove-quarantine-tags-in-powershell"></a>PowerShell で検疫タグを削除する

PowerShell を使用してカスタム検疫タグを削除する場合は、検疫タグの名前に置き換え、次の \<TagName\> コマンドを実行します。

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

構文およびパラメーターの詳細については [、「Remove-QuarantineTag」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag)。

## <a name="quarantine-tag-permission-details"></a>検疫タグのアクセス許可の詳細

以下のセクションでは、検疫済みメッセージの詳細およびエンド ユーザーのスパム通知における、事前設定されたアクセス許可グループと個々のアクセス許可の影響について説明します。

### <a name="preset-permissions-groups"></a>事前に設定されたアクセス許可グループ

既定のアクセス許可グループに含まれる個々のアクセス許可を、この記事の冒頭の表に示します。

#### <a name="no-access"></a>アクセスなし

検疫タグでアクセス許可なし(アクセス許可なし) が割り当てらた場合でも、ユーザーには次のベースライン機能があります。

- **検疫済みメッセージの詳細**: [ **メッセージ ヘッダーの表示]** ボタンは常に使用できます。

  ![検疫タグがユーザーにアクセス許可を与えがない場合に、検疫済みメッセージの詳細に表示される使用可能なボタン](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- **エンドユーザーのスパム通知**: 検疫 **内** のメッセージにユーザーを移動する [レビュー] ボタンは常に使用できます。

  ![検疫タグがユーザーにアクセス許可を与えがない場合に、エンド ユーザーのスパム通知で使用可能なボタン](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a>制限付きアクセス

検疫タグが制限付きアクセス許可を **割り当** てると、ユーザーは次の機能を利用できます。

- **検疫済みメッセージの詳細**: 次のボタンを使用できます。
  - **リリースを要求する**
  - **メッセージ ヘッダーの表示**
  - **プレビュー メッセージ**
  - **送信者をブロックする**
  - **検疫から削除する**

  ![検疫タグがユーザーに制限付きアクセス許可を与える場合、検疫済みメッセージの詳細で使用可能なボタン](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- **エンド ユーザーのスパム通知**: 次のボタンを使用できます。
  - **送信者をブロックする**
  - **確認**

  ![検疫タグがユーザーに制限付きアクセス許可を与える場合、エンド ユーザーのスパム通知で使用可能なボタン](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a>フル アクセス

検疫タグがフル アクセスの **アクセス許可** (使用可能なすべてのアクセス許可) を割り当てると、ユーザーは次の機能を利用できます。

- **検疫済みメッセージの詳細**: 次のボタンを使用できます。
  - **メッセージを解放する**
  - **メッセージ ヘッダーの表示**
  - **プレビュー メッセージ**
  - **送信者をブロックする**
  - **送信者を許可する**
  - **検疫から削除する**

  ![検疫タグがユーザーにフル アクセスのアクセス許可を与える場合、検疫済みメッセージの詳細で使用可能なボタン](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- **エンド ユーザーのスパム通知**: 次のボタンを使用できます。
  - **送信者をブロックする**
  - **Release**
  - **確認**

  ![検疫タグがユーザーにフル アクセスのアクセス許可を与える場合、エンド ユーザーのスパム通知で使用可能なボタン](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a>個々のアクセス許可

> [!NOTE]
> ユーザーには、常に「アクセスなし」セクションで説明されている [ボタンが表示](#no-access) されます。 これらのボタンは、個々のアクセス許可の説明には含まれません。

#### <a name="allow-sender-permission"></a>送信者のアクセス許可を許可する

送信者 **の許可**_(PermissionToAllowSender)_ は、検疫済みメッセージの送信者を安全な差出人のリストに簡単に追加できるボタンへのアクセスを制御します。

- **検疫済みメッセージの詳細**:
  - **[送信者のアクセス許可** を有効にする]: [送信者 **を許可する]** ボタンを使用できます。
  - **[送信者のアクセス** 許可を無効にする]: [送信者 **を許可する]** ボタンは使用できません。

- **エンドユーザーのスパム通知**: 効果なし。

差出人セーフ リストの詳細については、「信頼[](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666)できる差出人がブロックされるのを防ぐ」および[「Exchange Online PowerShell](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)を使用してメールボックスのセーフリスト コレクションを構成する」を参照してください。

#### <a name="block-sender-permission"></a>送信者のアクセス許可をブロックする

送信者 **のブロック** のアクセス許可 _(PermissionToBlockSender)_ は、ユーザーが検疫済みメッセージの送信者を受信拒否リストに簡単に追加できるボタンへのアクセスを制御します。

- **検疫済みメッセージの詳細**:
  - **[送信者のアクセス** 許可をブロックする] を有効にする: [送信者 **のブロック]** ボタンを使用できます。
  - **[送信者のアクセス** 許可をブロックする] が無効になっている: [送信者 **のブロック]** ボタンは使用できません。

- **エンドユーザーのスパム通知**:
  - **[送信者のアクセス** 許可をブロックする] が無効になっている: [送信者 **のブロック]** ボタンは使用できません。
  - **[送信者のアクセス** 許可をブロックする] を有効にする: [送信者 **のブロック]** ボタンを使用できます。

受信拒否リストの詳細については、「他のユーザーからのメッセージ[](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667)をブロックする」および[「Exchange Online PowerShell](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)を使用してメールボックスのセーフリスト コレクションを構成する」を参照してください。

#### <a name="delete-permission"></a>アクセス許可を削除する

削除 **アクセス** 許可 (_PermissionToDelete_) は、ユーザーが検疫からメッセージ (ユーザーが受信者であるメッセージ) を削除する機能を制御します。

- **検疫済みメッセージの詳細**:
  - **削除** のアクセス許可が有効になっている: [ **検疫から削除]** ボタンを使用できます。
  - **削除** のアクセス許可が無効になっている: [ **検疫から削除]** ボタンは使用できません。

- **エンドユーザーのスパム通知**: 効果なし。

#### <a name="preview-permission"></a>プレビューのアクセス許可

プレビュー **の** アクセス許可 _(PermissionToPreview)_ は、ユーザーが検疫でメッセージをプレビューする機能を制御します。

- **検疫済みメッセージの詳細**:
  - **プレビュー** のアクセス許可の有効化: **[メッセージのプレビュー]** ボタンを使用できます。
  - **プレビュー** のアクセス許可が無効になっている: **[メッセージのプレビュー]** ボタンは使用できません。

- **エンドユーザーのスパム通知**: 効果なし。

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a>受信者に検疫のアクセス許可からのメッセージの解放を許可する

受信者 **が** 検疫のアクセス許可 _(PermissionToRelease)_ からメッセージを解放する許可は、ユーザーが検疫済みメッセージを管理者の承認なしに直接解放する機能を制御します。

- **検疫済みメッセージの詳細**:
  - アクセス許可の有効化: **[メッセージの解放]** ボタンを使用できます。
  - アクセス許可が無効: **[メッセージの解放]** ボタンは使用できません。

- **エンドユーザーのスパム通知**:
  - アクセス許可の有効化: **[リリース]** ボタンを使用できます。
  - アクセス許可が無効: **[リリース** ] ボタンは使用できません。

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a>受信者が検疫のアクセス許可から解放されるメッセージを要求する

[**受信者に** 検疫からのメッセージの解放を要求する] アクセス許可 _(PermissionToRequestRelease)_ は、ユーザーが検疫済みメッセージの解放を要求する機能を制御します。 メッセージは、管理者が要求を承認した後にのみ解放されます。

- **検疫済みメッセージの詳細**:
  - アクセス許可の有効化: **[要求] リリース** ボタンを使用できます。
  - アクセス許可が無効: **[要求] リリース** ボタンは使用できません。

- **エンドユーザーのスパム通知**: [ **リリース]** ボタンは使用できません。
