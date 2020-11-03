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
description: 管理者は、検疫タグを使用して、検疫済みメッセージに対してユーザーが実行できる操作を制御する方法を学習できます。
ms.openlocfilehash: e50d7eea4cec3c87231dda855725b1e901f5fa33
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845698"
---
# <a name="quarantine-tags"></a>検疫タグ

> [!NOTE]
> この記事で説明されている機能は現在プレビュー段階であり、すべてのユーザーが利用できるわけではありません。変更される可能性があります。

Exchange Online Protection (EOP) の検疫タグは、検疫済みメッセージの受信方法に基づいて、ユーザーが検疫済みメッセージに対して実行できる操作を制御することを許可します。

EOP は、従来、 [検疫](find-and-release-quarantined-messages-as-a-user.md) のメッセージと [エンドユーザーのスパム通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)の特定のレベルの対話を許可または禁止しています。 たとえば、エンドユーザーはスパム対策フィルターによって検疫されたメッセージをスパムや一括で表示したり、解放したりすることはできますが、信頼性の高いフィッシングとして検疫されたメッセージを表示または解放することはできません。

[サポートされている保護機能](#step-2-assign-a-quarantine-tag-to-supported-features)については、検疫タグでは、エンドユーザーのスパム通知メッセージで許可されるユーザーと、検疫内の検疫済みメッセージ (ユーザーが受信者であるメッセージ) を指定します。 検疫済みメッセージに対してエンドユーザーの履歴機能を強制するために、既定の検疫タグが自動的に割り当てられます。 または、隔離されたメッセージに対してエンドユーザーが特定の操作を実行することを許可または禁止する、カスタムの検疫タグを作成して割り当てることができます。

個々のアクセス許可は、次の事前設定されたアクセス許可グループに統合されます。

- アクセスなし
- 制限付きアクセス
- フルアクセス

次の表では、使用可能な個々のアクセス許可と、事前設定されたアクセス許可グループに含まれているかどうかについて説明します。

|アクセス許可|アクセスなし|制限付きアクセス|フルアクセス|
|---|:---:|:---:|:---:|
|**送信者を許可する** ( _permissiontoallowsender_ )|||![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**受信拒否** ( _permissiontoblocksender_ )||![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**削除** ( _PermissionToDelete_ )||![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**プレビュー** ( _permissiontopreview_ )||![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**受信者が検疫からメッセージを解放することを許可する** ( _PermissionToRelease_ )|||![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**受信者が検疫から解放されるメッセージを要求できるように** する ( _PermissionToRequestRelease_ )||![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|

事前設定されたアクセス許可グループの既定のアクセス許可が気に入らない場合は、カスタムの検疫タグを作成または変更するときにカスタムアクセス許可を使用できます。 各アクセス許可の詳細については、この記事の後半の「 [検疫タグのアクセス許可の詳細](#quarantine-tag-permission-details) 」を参照してください。

検疫タグは、セキュリティ & コンプライアンスセンターまたは PowerShell (Microsoft 365 組織の exchange online PowerShell で exchange online メールボックスを使用しない EOP 組織では、exchange online のメールボックスを使用せずに、スタンドアロンの EOP PowerShell で作成および割り当てを行います。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [ **タグの検疫** ] ページに直接移動するには、を開き <https://protection.office.com/quarantineTags> ます。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- 検疫タグを表示、作成、変更、または削除するには、次のいずれかの役割グループのメンバーである必要があります。
  - **組織の管理** または [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の **セキュリティ管理者** 。
  - **組織の管理** または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の **検疫管理** 。

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a>手順 1: セキュリティ & コンプライアンスセンターで検疫タグを作成する

1. セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** ] に移動し、[ **タグの検疫** ] を選択します。

2. [ **タグの検疫** ] ページで、[ **カスタムタグの追加** ] を選択します。

3. [ **新しいタグ** ] ウィザードが開きます。 [ **タグ名** ] ページで、[ **タグ名** ] フィールドに簡単な一意の名前を入力します。 次の手順で、タグを識別して、名前で選択する必要があります。 完了したら、 **[次へ]** をクリックします。

4. [ **受信者メッセージアクセス** ] ページで、次のいずれかの値を選択します。
   - **アクセスなし**
   - **制限付きアクセス**
   - **フルアクセス**

   これらのアクセス許可グループに含まれる個々のアクセス許可については、この記事の前半で説明します。

   カスタムアクセス許可を指定するには、[特定のアクセス権を **設定 (詳細)** ] を選択し、次の設定を構成します。

     - **[リリースアクションの設定] を選択** します。次のいずれかの値を選択します。
       - [ **解放アクションなし** : これは既定値です。
       - **受信者が検疫からメッセージを解放することを許可する**
       - **受信者が検疫から解放されるメッセージを要求できるようにする**

     - **受信者が検疫済みメッセージに対して実行できる追加のアクションを選択** します。以下のいずれかの値を選択します。
       - **Delete**
       - **プレビュー**
       - **送信者を許可する**
       - **受信拒否**

   これらのアクセス許可と、エンドユーザーのスパム通知に対するこれらのアクセス許可とその影響については、この記事の後半の「 [検疫タグのアクセス許可の詳細](#quarantine-tag-permission-details) 」を参照してください。

   完了したら、 **[次へ]** をクリックします。

5. 表示される **要約** ページで、設定を確認します。 各設定で [ **編集** ] をクリックして、変更を行うことができます。

   完了したら、[ **送信** ] をクリックします。

6. 表示される確認ページで [ **完了** ] をクリックします。

これで、[ [ステップ 2](#step-2-assign-a-quarantine-tag-to-supported-features) ] セクションに記載されているように、検疫タグを検疫機能に割り当てる準備ができました。

### <a name="create-quarantine-tags-in-powershell"></a>PowerShell で検疫タグを作成する

PowerShell を使用して検疫タグを作成する場合は、Exchange Online PowerShell または Exchange Online Protection PowerShell に接続して、 **QuarantineTag** コマンドレットを使用します。 次の2種類の方法から選択できます。

- _EndUserQuarantinePermissionsValue_ パラメーターを使用します。
- _EndUserQuarantinePermissions_ パラメーターを使用します。

これらのメソッドについては、以下のセクションで説明します。

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a>EndUserQuarantinePermissionsValue パラメーターを使用する

_EndUserQuarantinePermissionsValue_ パラメーターを使用して検疫タグを作成するには、次の構文を使用します。

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

_EndUserQuarantinePermissionsValue_ パラメーターは、バイナリ値から変換された10進数の値を使用します。 Binary 値は、指定された順序で使用可能なエンドユーザーの検疫アクセス許可に対応します。 各アクセス許可について、値1は True になり、値0は False に等しくなります。

次の表では、事前設定されたアクセス許可グループの各アクセス許可に必要な順序と値について説明します。

****

|アクセス許可|アクセスなし|制限付きアクセス|フルアクセス|
|---|:---:|:---:|:---:|
|PermissionToAllowSender|.0|.0|1-d|
|PermissionToBlockSender|.0|1-d|1-d|
|PermissionToDelete|.0|1-d|1-d|
|PermissionToDownload<sup>\*</sup>|.0|.0|.0|
|PermissionToPreview|.0|1-d|1-d|
|PermissionToRelease<sup>\*\*</sup>|.0|.0|1-d|
|PermissionToRequestRelease<sup>\*\*</sup>|.0|1-d|.0|
|PermissionToViewHeader<sup>\*</sup>|.0|.0|.0|
|バイナリ値|00000000|01101010|11101100|
|使用する10進値|.0|106|236|

<sup>\*</sup> 現時点では、この値は常に0です。 PermissionToViewHeader の場合、値0を指定すると、検疫済みメッセージの詳細に [ **メッセージヘッダーの表示** ] ボタンが表示されません (ボタンは常に使用可能)。

<sup>\*\*</sup> 両方の値を1に設定しないでください。 1を1に設定し、もう一方を0に設定するか、または両方を0に設定します。

この例では、前の表で説明されているアクセス許可を割り当てずに、新しい検疫タグ名 NoAccess を作成します。

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

制限付きアクセスのアクセス許可の場合は、値106を使用します。 フルアクセスのアクセス許可については、値236を使用します。

カスタムアクセス許可の場合、前の表を使用して、必要なアクセス許可に対応するバイナリ値を取得します。 Binary 値を10進値に変換し、 _EndUserQuarantinePermissionsValue_ パラメーターに10進数の値を使用します。

構文およびパラメーターの詳細については、「 [QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)」を参照してください。

#### <a name="use-the-enduserquarantinepermissions-parameter"></a>EndUserQuarantinePermissions パラメーターを使用する

_EndUserQuarantinePermissionsValue_ パラメーターを使用して検疫タグを作成するには、次の手順を実行します。

A. **QuarantinePermissions** コマンドレットを使用して、変数に検疫アクセス許可オブジェクトを格納します。
<br/>
B. 変数は、 **QuarantineTag** コマンドの _EndUserQuarantinePermissions_ 値として使用します。

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a>手順 A: 検疫アクセス許可オブジェクトを変数に格納する

次の構文を使用してください。

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

使用されていないパラメーターの既定値は `$false` であるため、値をに設定するパラメーターのみを使用する必要があり `$true` ます。

次の例は、事前設定されたアクセス許可グループに対応する permission オブジェクトを作成する方法を示しています。

- **アクセス不可** :

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- **限定的なアクセス** :

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- **フルアクセス** :

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

設定した値を表示するには、変数名をコマンドとして実行します (たとえば、コマンドを実行し `$NoAccess` ます)。

カスタム権限の場合、 _PermissionToRelease_ パラメーターと _PermissionToRequestRelease_ パラメーターの両方をに設定しないで `$true` ください。 をに設定 `$true` してそのままにするか、のままにし `$false` `$false` ます。

また、 **QuarantinePermissions** コマンドレットを使用して、以前に作成した後で使用する前に、既存のアクセス許可オブジェクト変数を変更することもできます。

構文およびパラメーターの詳細については、「 [QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) 」および「 [QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions)」を参照してください。

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a>手順 B: New-QuarantineTag コマンドで変数を使用する

アクセス許可オブジェクトを作成して変数に格納した後、次の **QuarantineTag** コマンドで _EndUserQuarantinePermission_ パラメーターの値として変数を使用します。

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

この例では、 `$LimitedAccess` 前の手順で説明して作成したアクセス許可オブジェクトを使用して、LimitedAccess という名前の新しい quarantine タグを作成します。

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

構文およびパラメーターの詳細については、「 [QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)」を参照してください。

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a>手順 2: サポートされている機能に検疫タグを割り当てる

メッセージまたはファイルを検疫する、 _サポートされ_ ている保護機能 (自動または構成可能なアクションとして) では、検疫タグを利用可能な検疫アクションに割り当てることができます。 次の表では、メッセージを検疫し、検疫タグを使用できるようにする機能について説明します。

****

|機能|検疫タグはサポートされていますか?|使用される既定の検疫タグ|
|---|:---:|---|
|[スパム対策ポリシー](configure-your-spam-filter-policies.md): <ul><li>**スパム** ( _SpamAction_ )</li><li>**信頼度の高いスパム** ( _HighConfidenceSpamAction_ )</li><li>**フィッシング電子メール** ( _PhishSpamAction_ )</li><li>**高信頼フィッシング電子メール** ( _HighConfidencePhishAction_ )</li><li>**バルクメール** ( _BulkSpamAction_ )</li></ul>|はい|<ul><li>DefaultSpamTag (フルアクセス)</li><li>DefaultHighConfSpamTag (フルアクセス)</li><li>DefaultPhishTag (フルアクセス)</li><li>DefaultHighConfPhishTag (アクセス不可)</li><li>DefaultBulkTag (フルアクセス)</li></ul>
|フィッシング対策ポリシー: <ul><li>[スプーフィングインテリジェンス保護](set-up-anti-phishing-policies.md#spoof-settings) ( _authenticationfailaction_ )</li><li>[偽装保護](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup> <ul><li>**偽装ユーザーによって電子メールが送信される場合** ( _targeteduserprotectionaction_ )</li><li>**偽装ドメインによって電子メールが送信される場合** ( _targeteddomainprotectionaction_ )</li><li>**メールボックスインテリジェンス** \>**偽装ユーザーによって電子メールが送信される場合** ( _MailboxIntelligenceProtectionAction_ )</li></ul></li></ul></ul>|いいえ|該当なし|
|[マルウェア対策ポリシー](configure-anti-malware-policies.md): 検出されたすべてのメッセージが常に検疫されます。|いいえ|該当なし|
|[SharePoint、OneDrive、Microsoft Teams 用の ATP](atp-for-spo-odb-and-teams.md)|いいえ|該当なし|
|アクションを使用した [メールフロールール](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)(トランスポートルールとも呼ばれる): ホストされた検疫 ( _検疫_ ) **にメッセージを配信** します。|いいえ|該当なし|
|

<sup>\*</sup> 偽装保護の設定は、Microsoft Defender for Office 365 のフィッシング対策ポリシーでのみ使用できます。

既定の検疫タグで提供されるエンドユーザーのアクセス許可に満足している場合は、何もする必要はありません。 エンドユーザーのスパム通知または検疫されたメッセージの詳細でエンドユーザー機能 (利用可能なボタン) をカスタマイズする場合は、カスタム検疫タグを割り当てることができます。

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターのスパム対策ポリシーで検疫タグを割り当てる

スパム対策ポリシーを作成および変更する詳細な手順については、「 [CONFIGURE EOP」の「スパム対策ポリシーを構成](configure-your-spam-filter-policies.md)する」を参照してください。

1. [セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** ] に移動し \> てから、[ **スパム対策** ] を選択します。 または、を開き <https://protection.office.com/antispam> ます。

2. 編集する既存のスパム対策ポリシーを検索して選択するか、新しいスパム対策ポリシーを作成します。

3. ポリシーの詳細ポップアップで、[ **スパムと一括アクション** ] セクションを展開します。
  
4. [利用可能なスパムフィルター処理] verdict のアクションに対して [ **検疫メッセージ** ] を選択した場合、[ **検疫ポリシータグを適用** します] ボックスを使用して、その verdict の検疫タグを選択できます。

   **注** : 新しいポリシーを作成すると、スパムフィルター verdict の空の検疫タグ値は、その verdict が使用されている既定の quarantine タグを示します。 後でポリシーを編集すると、空の値は、前の表で説明したように、実際の既定の検査タグ名に置き換えられます。
  
   ![スパム対策ポリシーでのタグ選択の検疫](../../media/quarantine-tags-in-anti-spam-policies.png)

5. 完了したら、 **[保存]** をクリックします。

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a>PowerShell でスパム対策ポリシーの検疫タグを割り当てる

PowerShell を使用してスパム対策ポリシーで検疫タグを割り当てる場合は、Exchange Online PowerShell または Exchange Online Protection PowerShell に接続し、次の構文を使用します。

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

**注** :

- _HighConfidencePhishAction_ パラメーターの既定値は Quarantine なので、新しいスパム対策ポリシーで信頼度の高いフィッシングを検出するための検疫アクションを設定する必要はありません。 新規または既存のスパム対策ポリシーで、他のすべてのスパムフィルター verdicts の場合、検疫タグは、アクションの値が Quarantine の場合にのみ有効です。 既存のスパム対策ポリシーのアクション値を確認するには、次のコマンドを実行します。

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  標準および厳密の既定のアクション値および推奨されるアクション値の詳細については、「 [EOP spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)」を参照してください。

- スパムフィルター verdict に対応する quarantine タグパラメーターがない場合は、その verdict の [既定の quarantine タグ](#step-2-assign-a-quarantine-tag-to-supported-features) が使用されます。

  検疫されたメッセージに対する既定のエンドユーザーの機能を変更する場合は、既定の検疫タグをカスタム検疫タグに置き換えるだけで済みます。

- PowerShell の新しいスパム対策ポリシーには、 **set-hostedcontentfilterpolicy** コマンドレットを使用したスパムフィルターポリシー (設定) と、 **disable-hostedcontentfilterrule** コマンドレットを使用する新しいスパムフィルタールール (受信者フィルター) が必要です。 手順については、「 [PowerShell を使用してスパム対策ポリシーを作成する](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)」を参照してください。

この例では、Research Department という名前の新しいスパムフィルターポリシーを次の設定で作成します。

- すべてのスパムフィルタリング verdicts のアクションは、検疫に設定されます。
- **アクセス許可が** 割り当てられていない NoAccess という名前のカスタム検疫タグは、既定では、 **アクセス許可が** 割り当てられていない既定の検疫タグに置き換わります。

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

構文とパラメーターの詳細については、「[New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy)」を参照してください。

この例では、人的リソースという名前の既存のスパムフィルターポリシーを変更します。 スパム検疫 verdict のアクションは検疫に設定され、NoAccess という名前のカスタム検疫タグが割り当てられます。

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

構文とパラメーターの詳細については、「[Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)」を参照してください。

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターでのグローバル検疫通知設定の構成

検疫タグのグローバル設定を使用すると、検疫されたメッセージの受信者に送信されるエンドユーザーのスパム通知をカスタマイズできます。 これらの通知の詳細については、「 [エンドユーザーのスパム通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)」を参照してください。

1. セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** ] に移動し、[ **タグの検疫** ] を選択します。

2. [ **タグの検疫** ] ページで、[ **グローバル設定** ] を選択します。

3. [ **検疫通知の設定** ] ポップアップが表示されたら、次の設定の一部または全部を構成します。

   - **会社のロゴを使用** する: エンドユーザーのスパム通知の上位で使用されている既定の Microsoft ロゴを置き換えるには、このオプションを選択します。 この手順を実行する前に、「 [Microsoft 365 テーマをカスタマイズ](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) する」の「カスタムロゴをアップロードするには」の手順に従ってください。

     次のスクリーンショットは、エンドユーザーのスパム通知のカスタムロゴを示しています。

     ![エンドユーザーのスパム通知のカスタムロゴ](../../media/quarantine-tags-esn-customization-logo.png)

   - **言語の選択** : エンドユーザーのスパム通知は、受信者の言語設定に基づいて既にローカライズされています。 [ **表示名** ] と [ **免責事項** ] の値に対して、カスタマイズしたテキストをさまざまな言語で指定できます。

     [最初の言語] ボックスから少なくとも1つの言語を選択し、[ **追加** ] をクリックします。 複数の言語を選択するには、1つずつ [ **追加** ] をクリックします。 セクションの言語ボックスに、選択したすべての言語が表示されます。

     ![検疫タグのグローバル検疫通知設定の [2 番目の言語] ボックスで選択されている言語](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - [ **表示名** : エンドユーザーのスパム通知で使用される送信者の表示名をカスタマイズします。

     追加した言語ごとに、[2 番目の言語] ボックス ([X] をクリックしない) で言語を選択し、[ **表示名** ] ボックスに必要なテキスト値を入力します。

     次のスクリーンショットは、エンドユーザーのスパム通知のカスタマイズされた表示名を示しています。

     ![エンドユーザーのスパム通知にカスタマイズされた送信者の表示名](../../media/quarantine-tags-esn-customization-display-name.png)

   - **免責** 事項: エンドユーザーのスパム通知の下にカスタムの免責事項を追加します。 ローカライズされたテキスト、 **組織からの免責事項** は常に最初に含まれ、その後に指定するテキストが続きます。

     追加した言語ごとに、[2 番目の言語] ボックス ([X] をクリックしないでください) の言語を選択し、[ **免責事項** ] ボックスに必要なテキスト値を入力します。

     次のスクリーンショットは、エンドユーザーのスパム通知のカスタマイズされた免責事項を示しています。

     ![エンドユーザーのスパム通知の下部にあるカスタム免責事項](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターの検疫タグを表示する

1. セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** ] に移動し、[ **タグの検疫** ] を選択します。

- 組み込みまたはカスタムの検疫タグの設定を表示するには、リストから [quarantine] タグを選択します (チェックボックスをオンにしないでください)。

- グローバル設定を表示するには、[ **グローバル設定** ] を選択します。

### <a name="view-quarantine-tags-in-powershell"></a>PowerShell で検疫タグを表示する

PowerShell を使用して検疫タグを表示する場合は、次のいずれかの手順を実行します。

- すべての組み込みまたはカスタムタグの要約リストを表示するには、次のコマンドを実行します。

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- 組み込みまたはカスタムの検疫タグの設定を表示するには、を \<TagName\> quarantine タグの名前に置き換えて、次のコマンドを実行します。

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- グローバル設定を表示するには、次のコマンドを実行します。

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

構文とパラメーターの詳細については、「[Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy)」を参照してください。

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターで検疫タグを削除する

**注** :

- 組み込みの検疫タグを削除することはできません。

- カスタム検疫タグを削除する前に、そのタグが使用されていないことを確認してください。 たとえば、PowerShell で次のコマンドを実行します。

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  検疫タグが使用されている場合は、削除する前に、 [割り当てられている検疫タグを置き換え](#step-2-assign-a-quarantine-tag-to-supported-features) ます。

1. セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** ] に移動し、[ **タグの検疫** ] を選択します。

2. [ **タグの検疫** ] ページで、削除するカスタム検疫タグを選択し、[ **削除タグ** ] をクリックします。

3. 表示される確認ダイアログで、[ **タグの削除** ] をクリックします。

### <a name="remove-quarantine-tags-in-powershell"></a>PowerShell で検疫タグを削除する

PowerShell を使用してカスタム検疫タグを削除する場合は、を \<TagName\> quarantine タグの名前に置き換えて、次のコマンドを実行します。

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

構文およびパラメーターの詳細については、「 [QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag)」を参照してください。

## <a name="quarantine-tag-permission-details"></a>検疫タグのアクセス許可の詳細

次のセクションでは、事前設定されたメッセージとエンドユーザーのスパム通知の詳細に対する、事前設定されたアクセス許可グループと個々のアクセス許可の影響について説明します。

### <a name="preset-permissions-groups"></a>事前設定のアクセス許可グループ

事前設定されたアクセス許可グループに含まれる個々のアクセス許可を、この記事の冒頭の表に示します。

#### <a name="no-access"></a>アクセスなし

検疫タグが **アクセス許可なし** (アクセス許可なし) に割り当てられている場合でも、ユーザーには依然としていくつかの基準機能があります。

- **検疫済みメッセージの詳細** : [ **メッセージヘッダーの表示** ] ボタンは常に使用可能です。

  ![検疫タグによってユーザーにアクセス許可が付与されていない場合に、検疫済みメッセージの詳細で使用可能なボタン](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- **エンドユーザーのスパム通知** : 検疫中にユーザーにメッセージを表示する [ **確認** ] ボタンを常に使用できます。

  ![検疫タグでユーザーにアクセス許可が与えられていない場合、エンドユーザーのスパム通知で使用可能なボタン](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a>制限付きアクセス

検疫タグに **制限付きアクセス** のアクセス許可が割り当てられている場合、ユーザーは次の機能を利用できます。

- **検疫済みメッセージの詳細** : 次のボタンを使用できます。
  - **リリースの依頼**
  - **メッセージヘッダーを表示する**
  - **プレビューメッセージ**
  - **受信拒否**
  - **検疫から削除する**

  ![検疫タグによってユーザーに制限付きアクセスのアクセス許可が付与されている場合に、検疫済みメッセージの詳細で使用可能なボタン](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- **エンドユーザーのスパム通知** : 次のボタンが使用できます。
  - **受信拒否**
  - **確認**

  ![検疫タグでユーザーに制限付きアクセスのアクセス許可が付与されている場合、エンドユーザーのスパム通知で使用可能なボタン](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a>フルアクセス

検疫タグによって **フルアクセス** のアクセス許可 (利用可能なすべてのアクセス許可) が割り当てられている場合、ユーザーは次の機能を利用できます。

- **検疫済みメッセージの詳細** : 次のボタンを使用できます。
  - **メッセージを解放する**
  - **メッセージヘッダーを表示する**
  - **プレビューメッセージ**
  - **受信拒否**
  - **送信者を許可する**
  - **検疫から削除する**

  ![検疫タグによってユーザーにフルアクセスのアクセス許可が付与されている場合に、検疫済みメッセージの詳細で使用可能なボタン](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- **エンドユーザーのスパム通知** : 次のボタンが使用できます。
  - **受信拒否**
  - **リリース**
  - **確認**

  ![検疫タグでユーザーにフルアクセスのアクセス許可が付与されている場合、エンドユーザーのスパム通知で使用可能なボタン](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a>個別のアクセス許可

> [!NOTE]
> ユーザーが [ [アクセス不可](#no-access) ] セクションに表示されているボタンを常に取得することを覚えておいてください。 これらのボタンは、個々のアクセス許可の説明には含まれません。

#### <a name="allow-sender-permission"></a>送信者のアクセス許可を許可する

**送信者** のアクセス許可 ( _Permissiontoallowsender_ ) はボタンへのアクセスを制御します。これにより、ユーザーは検疫済みメッセージ送信者を安全な差出人のリストに簡単に追加できます。

- **検疫済みメッセージの詳細** :
  - [送信者アクセス許可を有効に **する** ]: [ **送信者を許可** する] ボタンを使用できます。
  - [ **送信者** のアクセス許可を無効にする]: [ **送信者を許可** する] ボタンは使用できません。

- **エンドユーザーのスパム通知** : 効果なし。

差出人セーフリストの詳細については、「 [信頼された送信者からのブロックを禁止](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) する」と「 [Exchange Online PowerShell を使用してメールボックスのセーフリストコレクションを構成する](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)」を参照してください。

#### <a name="block-sender-permission"></a>送信者のアクセス許可をブロックする

**送信者のブロック** アクセス許可 ( _Permissiontoblocksender_ ) は、ユーザーが検疫済みメッセージ送信者を受信拒否リストに簡単に追加できるようにするボタンへのアクセスを制御します。

- **検疫済みメッセージの詳細** :
  - [ **送信者のブロック** ] アクセス許可を有効にする: [送信者を **ブロック** する] ボタンを使用できます。
  - [ **送信者のブロック** ] アクセス許可を無効にする: [送信者を **ブロック** する] ボタンは使用できません。

- **エンドユーザーのスパム通知** :
  - [ **送信者のブロック** ] アクセス許可を無効にする: [送信者を **ブロック** する] ボタンは使用できません。
  - [ **送信者のブロック** ] アクセス許可を有効にする: [送信者を **ブロック** する] ボタンを使用できます。

受信拒否リストの詳細については、「 [ユーザーからのメッセージをブロック](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) する」と「 [Exchange Online の PowerShell を使用してメールボックスのセーフリストコレクションを構成する](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)」を参照してください。

#### <a name="delete-permission"></a>削除のアクセス許可

**Delete** アクセス許可 ( _PermissionToDelete_ ) は、検疫からユーザーが自分のメッセージ (ユーザーが受信者であるメッセージ) を削除する機能を制御します。

- **検疫済みメッセージの詳細** :
  - [ **削除** ] アクセス許可が有効: [ **検疫から削除** ] ボタンを使用できます。
  - **削除** 権限が無効: [ **検疫から削除** ] ボタンは使用できません。

- **エンドユーザーのスパム通知** : 効果なし。

#### <a name="preview-permission"></a>プレビューのアクセス許可

**プレビュー** アクセス許可 ( _permissiontopreview_ ) は、ユーザーが検疫でメッセージをプレビューできるかどうかを制御します。

- **検疫済みメッセージの詳細** :
  - **プレビュー** 権限が有効: [ **メッセージのプレビュー** ] ボタンを使用できます。
  - **プレビュー** アクセス許可が無効: [ **メッセージのプレビュー** ] ボタンは使用できません。

- **エンドユーザーのスパム通知** : 効果なし。

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a>受信者に検疫アクセス許可からメッセージを解放することを許可する

[ **受信者に検疫のメッセージを解放することを許可する** ] ( _PermissionToRelease_ ) は、ユーザーが、管理者の承認なしに、検疫済みメッセージを直接解放する機能を制御します。

- **検疫済みメッセージの詳細** :
  - アクセス許可: [ **メッセージの解放** ] ボタンを使用できます。
  - アクセス許可が無効: [ **メッセージの解放** ] ボタンは使用できません。
  
- **エンドユーザーのスパム通知** :
  - アクセス許可: [ **リリース** ] ボタンを使用できます。
  - アクセス許可が無効: **リリース** ボタンは使用できません。

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a>受信者が、検疫アクセス許可から解放されるメッセージを要求できるようにする

[受信者に検疫 (quarantine)] アクセス許可 ( _PermissionToRequestRelease_ ) **からメッセージを解放するよう要求する** ことで、ユーザーが検疫済みメッセージのリリースを _要求_ する機能を制御します。 このメッセージは、管理者が要求を承認した後にのみ解放されます。

- **検疫済みメッセージの詳細** :
  - アクセス許可: [ **リリースの要求** ] ボタンを使用できます。
  - アクセス許可が無効: [ **要求のリリース** ] ボタンは使用できません。

- **エンドユーザーのスパム通知** : [ **リリース** ] ボタンは使用できません。
