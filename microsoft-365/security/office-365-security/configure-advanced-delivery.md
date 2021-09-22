---
title: サードパーティのフィッシング シミュレーションをユーザーに配信し、フィルター処理されていないメッセージを SecOps メールボックスに配信する構成
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 管理者は、Exchange Online Protection (EOP) の高度な配信ポリシーを使用して、サポートされている特定のシナリオ (サード パーティのフィッシング シミュレーションとセキュリティ操作 (SecOps) メールボックスに配信されるメッセージ) でフィルター処理すべきではないメッセージを識別する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: baea981e712a02bfffb6b664d4bb6a3d8c9b5ae5
ms.sourcegitcommit: b295c60d5aa69781a20c59b9cdf2ed91c62b21af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2021
ms.locfileid: "59481050"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>サードパーティのフィッシング シミュレーションをユーザーに配信し、フィルター処理されていないメッセージを SecOps メールボックスに配信する構成

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

既定で組織を[](secure-by-default.md)セキュリティで保護するために、Exchange Online Protection (EOP) では、マルウェアまたは高信頼フィッシングとして識別されるメッセージの安全なリストやフィルター バイパスは許可されません。 ただし、フィルター処理されていないメッセージの配信を必要とする特定のシナリオがあります。 次に例を示します。

- **サード パーティのフィッシング シミュレーション**: シミュレートされた攻撃は、実際の攻撃が組織に影響を与える前に、脆弱なユーザーを特定するのに役立ちます。
- **セキュリティ操作 (SecOps)** メールボックス: セキュリティ チームがフィルター処理されていないメッセージ (良いメッセージと悪いメッセージの両方) を収集および分析するために使用する専用のメールボックス。

これらの特定の _シナリオの_ 受信メッセージMicrosoft 365を防ぐには、このサイトの高度な _配信ポリシーを_ 使用します。 <sup>\*</sup>高度な配信ポリシーにより、これらのシナリオのメッセージで次の結果が得られます。

- EOP と Microsoft Defender のフィルターは、Office 365に対してアクションを実行しません。<sup>\*</sup>
- [スパムとフィッシングのゼロアワー パージ (ZAP)](zero-hour-auto-purge.md) は、これらのメッセージに対して何も実行しません。<sup>\*</sup>
- [これらのシナリオでは](/microsoft-365/compliance/alert-policies#default-alert-policies) 、既定のシステム通知はトリガーされません。
- [Defender の AIR とクラスター化では、Office 365](office-365-air.md)メッセージは無視されます。
- 特に、サード パーティ製のフィッシング シミュレーションの場合:
  - [管理者の申請は](admin-submission.md) 、メッセージがフィッシング シミュレーション キャンペーンの一部であり、実際の脅威ではないという自動応答を生成します。 アラートと AIR はトリガーされません。 管理者の申請エクスペリエンスでは、これらのメッセージがシミュレートされた脅威として表示されます。
  - [ユーザー](enable-the-report-message-add-in.md)が Outlook のレポート フィッシング アドインを使用してフィッシング シミュレーション メッセージを報告した場合、システムはアラート、調査、インシデントを生成しない。 メッセージは、[申請] ページの [ユーザーが報告したメッセージ] タブにも表示されます。
  - [セーフ Defender for Office 365](safe-links.md)リンクは、クリック時にこれらのメッセージ内で特定された URL をブロックまたは削除しません。 URL はまだラップされますが、ブロックされません。
  - [セーフ Defender Office 365](safe-attachments.md)添付ファイルは、これらのメッセージ内の添付ファイルを削除しません。

<sup>\*</sup> マルウェアのフィルター処理やマルウェアに対する ZAP をバイパスできない。

高度な配信ポリシーによって識別されるメッセージはセキュリティ上の脅威ではないので、メッセージにはシステムオーバーライドがマークされます。 管理者エクスペリエンスでは、フィッシング シミュレーション システムのオーバーライドまたは SecOps メールボックス システムの上書きにより、これらの **メッセージが** 表示されます。 管理者は、次のエクスペリエンスで、これらのシステムオーバーライドをフィルター処理して分析できます。

- [Defender for Office 365](threat-explorer.md)プラン 2 の脅威エクスプローラー/リアルタイム検出 : 管理者は、システムオーバーライド ソースでフィルター処理し、フィッシング シミュレーションまたは **SecOps メールボックスを選択できます**。
- 脅威 [エクスプローラー/](mdo-email-entity-page.md)リアルタイム検出のメール エンティティ ページ : 管理者は、[オーバーライド **]** セクションの [テナントの上書き] の下で **、SecOps** メールボックスまたはフィッシング シミュレーションによって組織ポリシーによって許可されたメッセージを表示できます。
- 脅威 [保護の状態](view-email-security-reports.md#threat-protection-status-report)レポート : 管理者は、ドロップダウン メニューの **システム** オーバーライドによってビュー データをフィルター処理し、フィッシング シミュレーション システムの上書きによって許可されるメッセージを表示する場合に選択できます。 SecOps メールボックスの上書きで許可されるメッセージを表示するには、[理由] ドロップダウン メニューの [グラフの内訳] で、配信場所別にグラフの **内訳を選択** できます。
- [Microsoft Defender for Endpoint](../defender-endpoint/advanced-hunting-overview.md)での高度な検索 : フィッシング シミュレーションと SecOps メールボックス システムの上書きは、EmailEvents の OrgLevelPolicy 内のオプションとして表示されます。
- [キャンペーン ビュー](campaigns.md): 管理者は、システム オーバーライド ソース **を** フィルター処理し、 **フィッシング** シミュレーションまたは **SecOps メールボックスを選択できます**。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 [高度な配信] ページに **直接移動するには** 、を開きます <https://security.microsoft.com/advanceddelivery> 。

- セキュリティ/コンプライアンス センターの PowerShell に接続するには、「[セキュリティ/コンプライアンス センター PowerShell に接続する](/powershell/exchange/connect-to-scc-powershell)」を参照してください。

- この記事の手順を実行するには、アクセス許可を割り当てる必要があります。
  - 高度な配信ポリシーで構成された設定を作成、変更、または削除するには、Microsoft 365 Defender ポータルのセキュリティ管理者役割グループのメンバーであり **、Exchange Online** の組織の管理役割グループ **のメンバーである必要があります**。
  - 高度な配信ポリシーへの読み取り専用アクセスでは、グローバル リーダーまたはセキュリティリーダーの役割グループの **メンバーである** 必要があります。

  詳細については、「Microsoft 365 Defender[](permissions-microsoft-365-security-center.md)ポータルのアクセス許可」および「Exchange Online」[を参照してください](/exchange/permissions-exo/permissions-exo)。

  > [!NOTE]
  > ユーザーを対応する Azure Active Directory ロールに追加すると、ユーザーは Microsoft 365 Defender ポータルで必要なアクセス許可と、Microsoft 365 の他の機能に対するアクセス許可を与Microsoft 365。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>高度な配信Microsoft 365 Defender SecOps メールボックスを構成するには、次のポータルを使用します。

1. [ルール] Microsoft 365 Defenderで、[ルール]セクションの&ルールの脅威&詳細な配信を電子メールで送信する] \>  \>  \> **に移動** します。

2. [高度 **な配信] ページ** で **、[SecOps** メールボックス] タブが選択されていることを確認し、次のいずれかの手順を実行します。
   - [編集 ![ ] アイコンをクリックします。](../../media/m365-cc-sc-edit-icon.png) **編集**。
   - フィッシング シミュレーションが構成されていない場合は、[追加] を **クリックします**。

3. 開く **[SecOps** メールボックスの編集] フライアウトで、次のいずれかの手順を実行して、SecOps メールボックスとして指定する既存の Exchange Online メールボックスを入力します。
   - ボックス内をクリックし、メールボックスの一覧を解決し、メールボックスを選択します。
   - ボックス内をクリックすると、メールボックスの識別子 (名前、表示名、エイリアス、電子メール アドレス、アカウント名など) の入力を開始し、結果からメールボックス (表示名) を選択します。

     必要な回数だけこの手順を繰り返します。 配布グループは許可されません。

     既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

4. 完了したら、**[保存]** をクリックします。

構成した SecOps メールボックス エントリは **、[SecOps** メールボックス] タブに表示されます。変更するには、[編集] アイコン ![ をクリックします。](../../media/m365-cc-sc-edit-icon.png) **タブ** の [編集] をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>高度な配信Microsoft 365 Defenderでサード パーティのフィッシング シミュレーションを構成するには、Microsoft 365 Defender ポータルを使用します。

1. [ルール] Microsoft 365 Defenderで、[ルール]セクションの&ルールの脅威&詳細な配信を電子メールで送信する] \>  \>  \> **に移動** します。

2. [高度 **な配信] ページ** で、[フィッシング シミュレーション] **タブを選択** し、次のいずれかの手順を実行します。
   - [編集 ![ ] アイコンをクリックします。](../../media/m365-cc-sc-edit-icon.png) **編集**。
   - フィッシング シミュレーションが構成されていない場合は、[追加] を **クリックします**。

3. 開く **[サード パーティ製フィッシング シミュレーションの編集] フライ** アウトで、次の設定を構成します。

   - **ドメイン**: この設定を展開し、ボックスをクリックして値を入力し、Enter キーを押するか、ボックスの下に表示される値を選択して、少なくとも 1 つの電子メール アドレス ドメイン (contoso.com など) を入力します。 必要な回数だけこの手順を繰り返します。 最大 10 のエントリを追加できます。

     > [!NOTE]
     > フィッシング シミュレーション ベンダーによって指定されたメッセージまたは `5321.MailFrom` DomainKeys Identified Mail (DKIM) ドメインの SMTP 送信で使用されるアドレス **(MAIL FROM** アドレス、P1 送信者、封筒送信者とも呼ばれる) のドメインを使用します。 

   - **送信 IP**: この設定を展開し、ボックスをクリックして値を入力し、Enter キーを押するか、ボックスの下に表示される値を選択して、少なくとも 1 つの有効な IPv4 アドレスを入力します。 必要な回数だけこの手順を繰り返します。 最大 10 のエントリを追加できます。 有効な値は次のとおりです。
     - 単一 IP: たとえば、192.168.1.1。
     - IP 範囲: たとえば、192.168.0.1-192.168.0.254 です。
     - CIDR IP: たとえば、192.168.0.1/25。
   - **許可** するシミュレーション URL : この設定を展開し、必要に応じて、フィッシング シミュレーション キャンペーンの一部である特定の URL を入力します。この URL は、ボックス内をクリックして値を入力し、Enter キーを押したり、ボックスの下に表示される値を選択したりしてブロックまたは削除する必要があります。 最大 10 のエントリを追加できます。 URL 構文の形式については、「テナント許可/ブロック一覧」の URL 構文 [を参照してください](tenant-allow-block-list.md#url-syntax-for-the-tenant-allowblock-list)。 これらの URL はクリック時にラップされますが、ブロックされません。

   既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

   > [!NOTE]
   > Advanced Delivery でサード パーティのフィッシング シミュレーションを構成するには、次の情報を提供する必要があります。
   > 
   > - 次のいずれかのソース **から** 少なくとも 1 つのドメイン。
   >   - アドレス (MAIL FROM アドレス、P1 送信者、封筒送信者とも `5321.MailFrom` 呼ばれる)。
   >   - DKIM ドメイン。
   > - 少なくとも 1 **つの送信 IP**。
   > 
   > 必要に応じて **、シミュレーション URL** を含め、シミュレーション メッセージ内の URL がブロックされません。
   > 各フィールドに最大 10 のエントリを指定できます。
   > 少なくとも 1 つのドメインと **1** つの送信 **IP** に一致する必要がありますが、値間の関連付けは維持されません。

4. 完了したら、次のいずれかの手順を実行します。
   - **初回:**[追加] を **クリックし**、[閉じる] を **クリックします**。
   - **既存の編集 :**[保存] を **クリックし** 、[閉じる] を **クリックします**。

構成したサード パーティのフィッシング シミュレーション エントリが [フィッシング シミュレーション] **タブに表示** されます。変更するには、[編集] アイコン ![ をクリックします。](../../media/m365-cc-sc-edit-icon.png) **タブ** の [編集] をクリックします。

## <a name="additional-scenarios-that-require-filtering-bypass"></a>フィルター バイパスが必要なその他のシナリオ

高度な配信ポリシーが役立つ 2 つのシナリオに加えて、フィルター処理をバイパスする必要がある他のシナリオがあります。

- **サード パーティ製フィルター**: ドメインの MXレコードが Office 365 を指していない場合 (メッセージは最初にどこか別の [](secure-by-default.md)場所にルーティングされます)、既定ではセキュリティで保護 *されません。* 保護を追加する場合は、コネクタの拡張フィルター (スキップ リストとも呼ばれる) を有効にする *必要があります*。 詳細については、「サードパーティのクラウド サービスを使用してメール フローを管理する」を参照[Exchange Online。](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud) コネクタの拡張フィルター処理を使用しない場合は、メール フロー ルール (トランスポート ルールとも呼ばれる) を使用して、サード パーティ製のフィルター処理によって既に評価されているメッセージに対して Microsoft のフィルター処理をバイパスします。 詳細については、「メール フロー ルール [を使用してメッセージの SCL を設定する」を参照してください](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)。

- **レビュー中** の誤検知 : 管理者の申請を通じて Microsoft によって分析中の特定の [](admin-submission.md)メッセージを一時的に許可して、Microsoft に不適切とマークされている既知の良いメッセージ (誤検知) を報告することができます。 すべての上書きと同様に、これらの許容量 **_は_** 一時的なものとすることを強くお勧めします。

## <a name="security--compliance-center-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a>セキュリティ&高度な配信ポリシーの SecOps メールボックスのコンプライアンス センター PowerShell の手順

セキュリティ コンプライアンス & PowerShell では、高度な配信ポリシーの SecOps メールボックスの基本的な要素は次のとおりです。

- **SecOps オーバーライド ポリシー**: **\* -SecOpsOverridePolicy コマンドレットによって** 制御されます。
- **SecOps オーバーライド ルール**: **\* -SecOpsOverrideRule** コマンドレットによって制御されます。

この動作の結果は次のとおりです。

- 最初にポリシーを作成してから、ルールが適用されるポリシーを識別するルールを作成します。
- PowerShell からポリシーを削除すると、対応するルールも削除されます。
- PowerShell からルールを削除すると、対応するポリシーは削除されません。 対応するポリシーを手動で削除する必要があります。

### <a name="use-powershell-to-configure-secops-mailboxes"></a>PowerShell を使用して SecOps メールボックスを構成する

PowerShell の高度な配信ポリシーで SecOps メールボックスを構成するには、次の 2 つの手順を実行します。

1. SecOps オーバーライド ポリシーを作成します。
2. ルールが適用されるポリシーを指定する SecOps オーバーライド ルールを作成します。

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a>手順 1: PowerShell を使用して SecOps オーバーライド ポリシーを作成する

SecOps オーバーライド ポリシーを作成するには、次の構文を使用します。

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

> [!NOTE]
> 指定した Name 値に関係なく、ポリシー名は _SecOpsOverridePolicy_ なので、その値を使用することもできます。

次の使用例は、SecOps メールボックス ポリシーを作成します。

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo secops@contoso.com
```

構文とパラメーターの詳細については [、「New-SecOpsOverridePolicy」を参照してください](/powershell/module/exchange/new-secopsoverridepolicy)。

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a>手順 2: PowerShell を使用して SecOps オーバーライド ルールを作成する

次の使用例は、指定した設定で SecOps メールボックス ルールを作成します。

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

> [!NOTE]
> 指定した Name 値に関係なく、ルール名は _SecOpsOverrideRule_ になります。これは一意の GUID 値 \<GUID\> \<GUID\> です (たとえば、6fed4b63-3563-495d-a481-b24a311f8329 など)。

構文とパラメーターの詳細については [、「New-SecOpsOverrideRule」を参照してください](/powershell/module/exchange/new-secopsoverriderule)。

### <a name="use-powershell-to-view-the-secops-override-policy"></a>PowerShell を使用して SecOps オーバーライド ポリシーを表示する

次の使用例は、1 つの SecOps メールボックス ポリシーに関する詳細情報を返します。

```powershell
Get-SecOpsOverridePolicy
```

構文とパラメーターの詳細については [、「Get-SecOpsOverridePolicy」を参照してください](/powershell/module/exchange/get-secopsoverridepolicy)。

### <a name="use-powershell-to-view-secops-override-rules"></a>PowerShell を使用して SecOps オーバーライド ルールを表示する

次の使用例は、SecOps オーバーライド ルールに関する詳細情報を返します。

```powershell
Get-SecOpsOverrideRule
```

前のコマンドは 1 つのルールのみを返す必要があります。削除が保留中のルールも結果に含まれる可能性があります。

次の使用例は、有効なルール (1) と無効なルールを識別します。

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

無効なルールを特定した後、この記事で後述するように **Remove-SecOpsOverrideRule** コマンドレットを使用して削除 [できます](#use-powershell-to-remove-secops-override-rules)。

構文とパラメーターの詳細については [、「Get-SecOpsOverrideRule」を参照してください](/powershell/module/exchange/get-secopsoverriderule)。

### <a name="use-powershell-to-modify-the-secops-override-policy"></a>PowerShell を使用して SecOps オーバーライド ポリシーを変更する

SecOps オーバーライド ポリシーを変更するには、次の構文を使用します。

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

次の使用例 `secops2@contoso.com` は、SecOps オーバーライド ポリシーに追加します。

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

> [!NOTE]
> 関連付けられた有効な SecOps オーバーライド ルールが存在する場合、ルール内の電子メール アドレスも更新されます。

構文とパラメーターの詳細については [、「Set-SecOpsOverridePolicy」を参照してください](/powershell/module/exchange/set-secopsoverridepolicy)。

### <a name="use-powershell-to-modify-a-secops-override-rule"></a>PowerShell を使用して SecOps オーバーライド ルールを変更する

**Set-SecOpsOverrideRule** コマンドレットは、SecOps オーバーライド ルールの電子メール アドレスを変更しません。 SecOps オーバーライド ルールの電子メール アドレスを変更するには **、Set-SecOpsOverridePolicy コマンドレットを使用** します。

構文とパラメーターの詳細については [、「Set-SecOpsOverrideRule」を参照してください](/powershell/module/exchange/set-secopsoverriderule)。

### <a name="use-powershell-to-remove-the-secops-override-policy"></a>PowerShell を使用して SecOps オーバーライド ポリシーを削除する

次の使用例は、SecOps メールボックス ポリシーと対応するルールを削除します。

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

構文とパラメーターの詳細については [、「Remove-SecOpsOverridePolicy」を参照してください](/powershell/module/exchange/remove-secopsoverridepolicy)。

### <a name="use-powershell-to-remove-secops-override-rules"></a>PowerShell を使用して SecOps オーバーライド ルールを削除する

SecOps オーバーライド ルールを削除するには、次の構文を使用します。

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

次の使用例は、指定した SecOps オーバーライド ルールを削除します。

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

構文とパラメーターの詳細については [、「Remove-SecOpsOverrideRule」を参照してください](/powershell/module/exchange/remove-secopsoverriderule)。

## <a name="security--compliance-center-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>高度&におけるサード パーティのフィッシング シミュレーションに関するコンプライアンス センター PowerShell のセキュリティ手順

セキュリティ & コンプライアンス センター PowerShell では、高度な配信ポリシーのサード パーティフィッシング シミュレーションの基本的な要素は次のとおりです。

- **フィッシング シミュレーションの上書きポリシー**: **\* -PhishSimOverridePolicy** コマンドレットによって制御されます。
- **フィッシング シミュレーションの上書きルール**: **\* -PhishSimOverrideRule** コマンドレットによって制御されます。
- **許可されている (ブロックされていない)** フィッシング シミュレーション URL : **\* -TenantAllowBlockListItems** コマンドレットによって制御されます。

この動作の結果は次のとおりです。

- 最初にポリシーを作成してから、ルールが適用されるポリシーを識別するルールを作成します。
- ポリシーとルールの設定は個別に変更します。
- PowerShell からポリシーを削除すると、対応するルールも削除されます。
- PowerShell からルールを削除すると、対応するポリシーは削除されません。 対応するポリシーを手動で削除する必要があります。

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a>PowerShell を使用してサード パーティのフィッシング シミュレーションを構成する

PowerShell でサード パーティ製のフィッシング シミュレーションを構成するには、次の複数の手順を実行します。

1. フィッシング シミュレーションオーバーライド ポリシーを作成します。
2. 次の値を指定するフィッシング シミュレーションオーバーライド ルールを作成します。
   - ルールが適用されるポリシー。
   - フィッシング シミュレーション メッセージの送信元 IP アドレス。
3. 必要に応じて、許可する必要があるフィッシング シミュレーション URL (ブロックまたはスキャンされていない) を識別します。

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a>手順 1: PowerShell を使用してフィッシング シミュレーションオーバーライド ポリシーを作成する

この例では、フィッシング シミュレーションオーバーライド ポリシーを作成します。

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

**注**: 指定した Name 値に関係なく、ポリシー名は _PhishSimOverridePolicy_ なので、その値を使用することもできます。

構文とパラメーターの詳細については [、「New-PhishSimOverridePolicy」を参照してください](/powershell/module/exchange/new-phishsimoverridepolicy)。

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a>手順 2: PowerShell を使用してフィッシング シミュレーションオーバーライド ルールを作成する

次の構文を使用してください。

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs <Domain1>,<Domain2>,...<DomainN> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>
```

指定した Name 値に関係なく、ルール名は、一意の GUID 値である _PhishSimOverrideRule_ \<GUID\> になります (たとえば \<GUID\> 、a0eae53e-d755-4a42-9320-b9c6b55c5011 など)。

有効な IP アドレス エントリは、次のいずれかの値です。

- 単一 IP: たとえば、192.168.1.1。
- IP 範囲: たとえば、192.168.0.1-192.168.0.254 です。
- CIDR IP: たとえば、192.168.0.1/25。

次の使用例は、指定した設定でフィッシング シミュレーションオーバーライド ルールを作成します。

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

構文とパラメーターの詳細については [、「New-PhishSimOverrideRule」を参照してください](/powershell/module/exchange/new-phishsimoverriderule)。

#### <a name="step-3-optional-use-powershell-to-identify-the-phishing-simulation-urls-to-allow"></a>手順 3: (オプション) PowerShell を使用してフィッシング シミュレーション URL を識別して許可する

次の構文を使用してください。

```powershell
New-TenantAllowBlockListItems -Allow -ListType Url -ListSubType AdvancedDelivery -Entries "<URL1>","<URL2>",..."<URLN>" <[-NoExpiration] | [-ExpirationDate <DateTime>]>
```

URL 構文の詳細については、「テナント許可/ブロック一 [覧の URL 構文」を参照してください](tenant-allow-block-list.md#url-syntax-for-the-tenant-allowblock-list)。

次の使用例は、有効期限が切れない、指定されたサード パーティフィッシング シミュレーション URL の URL 許可エントリを追加します。

```powershell
New-TenantAllowBlockListItems -Allow -ListType Url -ListSubType AdvancedDelivery -Entries *.fabrikam.com -NoExpiration
```

構文とパラメーターの詳細については [、「New-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/new-tenantallowblocklistitems)。

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a>PowerShell を使用してフィッシング シミュレーションオーバーライド ポリシーを表示する

この例では、唯一のフィッシング シミュレーションオーバーライド ポリシーに関する詳細情報を返します。

```powershell
Get-PhishSimOverridePolicy
```

構文とパラメーターの詳細については [、「Get-PhishSimOverridePolicy」を参照してください](/powershell/module/exchange/get-phishsimoverridepolicy)。

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a>PowerShell を使用してフィッシング シミュレーションの上書きルールを表示する

この例では、フィッシング シミュレーションの上書きルールに関する詳細情報を返します。

```powershell
Get-PhishSimOverrideRule
```

前のコマンドは 1 つのルールのみを返す必要があります。削除が保留中のルールも結果に含まれる可能性があります。

次の使用例は、有効なルール (1) と無効なルールを識別します。

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

無効なルールを特定した後、この記事で後述するように **Remove-PhishSimOverrideRule** コマンドレットを使用して削除 [できます](#use-powershell-to-remove-phishing-simulation-override-rules)。

構文とパラメーターの詳細については [、「Get-PhishSimOverrideRule」を参照してください](/powershell/module/exchange/get-phishsimoverriderule)。

### <a name="use-powershell-to-view-the-allowed-phishing-simulation-url-entries"></a>PowerShell を使用して、許可されているフィッシング シミュレーション URL エントリを表示する

許可されているフィッシング シミュレーション URL を表示するには、次のコマンドを実行します。

```powershell
Get-TenantAllowBlockListItems -ListType Url -ListSubType AdvancedDelivery
```

構文とパラメーターの詳細については [、「Get-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/get-tenantallowblocklistitems)。

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a>PowerShell を使用してフィッシング シミュレーションオーバーライド ポリシーを変更する

フィッシング シミュレーションオーバーライド ポリシーを変更するには、次の構文を使用します。

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

この例では、フィッシング シミュレーションオーバーライド ポリシーを無効にします。

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

構文とパラメーターの詳細については [、「Set-PhishSimOverridePolicy」を参照してください](/powershell/module/exchange/set-phishsimoverridepolicy)。

### <a name="use-powershell-to-modify-phishing-simulation-override-rules"></a>PowerShell を使用してフィッシング シミュレーションの上書きルールを変更する

フィッシング シミュレーションオーバーライド ルールを変更するには、次の構文を使用します。

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

次の使用例は、次の設定を使用して、指定したフィッシング シミュレーションオーバーライド ルールを変更します。

- ドメイン エントリを追加 blueyonderairlines.com。
- IP アドレス エントリ 192.168.1.55 を削除します。

これらの変更は既存のエントリには影響しない点に注意してください。

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

構文とパラメーターの詳細については [、「Set-PhishSimOverrideRule」を参照してください](/powershell/module/exchange/set-phishsimoverriderule)。

### <a name="use-powershell-to-modify-the-allowed-phishing-simulation-url-entries"></a>PowerShell を使用して、許可されているフィッシング シミュレーション URL エントリを変更する

URL 値を直接変更することはできません。 この記事 [の説明に従って、既存の URL](#use-powershell-to-remove-the-allowed-phishing-simulation-url-entries) エントリを削除し、 [新しい URL](#step-3-optional-use-powershell-to-identify-the-phishing-simulation-urls-to-allow) エントリを追加できます。

許可されているフィッシング シミュレーション URL エントリの他のプロパティ (有効期限やコメントなど) を変更するには、次の構文を使用します。

```powershell
Set-TenantAllowBlockListItems <-Entries "<URL1>","<URL2>",..."<URLN>" | -Ids <Identity>> -ListType URL -ListSubType AdvancedDelivery <[-NoExpiration] | [-ExpirationDate <DateTime>]> [-Notes <String>]
```

変更するエントリは、その URL 値 _(Entrys_ パラメーター) または **Get-TenantAllowBlockListItems** コマンドレット _(Ids_ パラメーター) の出力から識別します。

次の使用例は、指定したエントリの有効期限を変更しました。

```powershell
Set-TenantAllowBlockListItems -ListType Url -ListSubType AdvancedDelivery –Entries "*.fabrikam.com" -ExpirationDate 9/11/2021
```

構文とパラメーターの詳細については [、「Set-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/set-tenantallowblocklistitems)。

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a>PowerShell を使用してフィッシング シミュレーションオーバーライド ポリシーを削除する

次の使用例は、フィッシング シミュレーションオーバーライド ポリシーと対応するルールを削除します。

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

構文とパラメーターの詳細については [、「Remove-PhishSimOverridePolicy」を参照してください](/powershell/module/exchange/remove-phishsimoverridepolicy)。

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a>PowerShell を使用してフィッシング シミュレーションの上書きルールを削除する

フィッシング シミュレーションオーバーライド ルールを削除するには、次の構文を使用します。

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

次の使用例は、指定したフィッシング シミュレーションオーバーライド ルールを削除します。

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

構文とパラメーターの詳細については [、「Remove-PhishSimOverrideRule」を参照してください](/powershell/module/exchange/remove-phishsimoverriderule)。

### <a name="use-powershell-to-remove-the-allowed-phishing-simulation-url-entries"></a>PowerShell を使用して、許可されているフィッシング シミュレーション URL エントリを削除する

既存のフィッシング シミュレーション URL エントリを削除するには、次の構文を使用します。

```powershell
Remove-TenantAllowBlockListItems <-Entries "<URL1>","<URL2>",..."<URLN>" | -Ids <Identity>> -ListType URL -ListSubType AdvancedDelivery
```

変更するエントリは、その URL 値 _(Entrys_ パラメーター) または **Get-TenantAllowBlockListItems** コマンドレット _(Ids_ パラメーター) の出力から識別します。

次の使用例は、指定したエントリの有効期限を変更しました。

```powershell
Remove-TenantAllowBlockListItems -ListType Url -ListSubType AdvancedDelivery –Entries "*.fabrikam.com" -ExpirationDate 9/11/2021
```

構文とパラメーターの詳細については [、「Remove-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/remove-tenantallowblocklistitems)。

