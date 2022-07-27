---
title: サードパーティのフィッシング シミュレーションをユーザーに配信し、フィルター処理されていないメッセージを SecOps メールボックスに配信するように構成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 管理者は、Exchange Online Protection (EOP) の高度な配信ポリシーを使用して、サポートされている特定のシナリオ (サード パーティのフィッシング シミュレーションとセキュリティ操作 (SecOps) メールボックスに配信されるメッセージ) でフィルター処理すべきでないメッセージを特定する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b69e143ecae2974db249a64d32d18cb5ead32aa6
ms.sourcegitcommit: e8dd5cd434d17af7096d28d467a2b3b021cbb233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "67051186"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>サードパーティのフィッシング シミュレーションをユーザーに配信し、フィルター処理されていないメッセージを SecOps メールボックスに配信するように構成する

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[組織を既定でセキュリティで保護](secure-by-default.md)するために、Exchange Online Protection (EOP) では、マルウェアまたは信頼度の高いフィッシングとして識別されるメッセージのセーフ リストまたはフィルター処理のバイパスは許可されません。 ただし、フィルター処理されていないメッセージの配信を必要とする特定のシナリオがあります。 以下に例を示します。

- **サード パーティのフィッシング シミュレーション**: シミュレートされた攻撃は、実際の攻撃が組織に影響を与える前に、脆弱なユーザーを特定するのに役立ちます。
- **セキュリティ操作 (SecOps) メールボックス**: フィルター処理されていないメッセージ (良いメッセージと悪いメッセージの両方) を収集および分析するためにセキュリティ チームによって使用される専用メールボックス。

Microsoft 365 の _高度な配信ポリシー_ を使用して、 _これらの特定のシナリオで_ 受信メッセージがフィルター処理 <sup>\*</sup>されないようにします。 高度な配信ポリシーを使用すると、これらのシナリオのメッセージで次の結果が得られます。

- EOP とMicrosoft Defender for Office 365のフィルターは、これらのメッセージに対して何のアクションも実行しません。<sup>\*</sup>
- スパムとフィッシングの[ゼロ時間消去 (ZAP)](zero-hour-auto-purge.md) では、これらのメッセージ<sup>\*\*</sup>に対してアクションは実行されません。
- これらのシナリオでは、[既定のシステム アラート](/microsoft-365/compliance/alert-policies#default-alert-policies)はトリガーされません。
- [Defender for Office 365の AIR とクラスタリングでは](office-365-air.md)、これらのメッセージは無視されます。
- 特にサード パーティのフィッシング シミュレーションの場合:
  - [管理送信では、](admin-submission.md)メッセージがフィッシング シミュレーション キャンペーンの一部であり、実際の脅威ではないことを示す自動応答が生成されます。 アラートと AIR はトリガーされません。 管理者の提出エクスペリエンスでは、これらのメッセージがシミュレートされた脅威として表示されます。
  - ユーザーがレポート メッセージまたはレポート フィッシング アドインを使用してフィッシング シミュレーション [メッセージを報告](enable-the-report-message-add-in.md)すると、システムはアラート、調査、またはインシデントを生成しません。 リンクまたはファイルは起爆されませんが、メッセージは **[送信]** ページの [**ユーザーが報告したメッセージ**] タブにも表示されます。
  - [Defender for Office 365のセーフ リンク](safe-links.md)では、クリック時にこれらのメッセージ内の特定の URL がブロックまたは爆発することはありません。 URL は引き続きラップされますが、ブロックされません。
  - [Defender for Office 365の安全な添付ファイル](safe-attachments.md)は、これらのメッセージの添付ファイルを爆発させません。

<sup>\*</sup> マルウェア のフィルター処理をバイパスすることはできません。

<sup>\*\*</sup> マルウェアの ZAP をバイパスするには、マルウェアの ZAP がオフになっている SecOps メールボックスのマルウェア対策ポリシーを作成します。 手順については、「 [EOP でマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)」を参照してください。

高度な配信ポリシーによって識別されるメッセージはセキュリティ上の脅威ではないため、メッセージはシステムオーバーライドでマークされます。 管理エクスペリエンスでは、**フィッシング シミュレーション** システムのオーバーライドまたは **SecOps メールボックス** システムのオーバーライドのいずれかが原因で、これらのメッセージが表示されます。 管理者は、次のエクスペリエンスで、これらのシステムオーバーライドをフィルター処理して分析できます。

- [Defender for Office 365プラン 2 の脅威エクスプローラー/リアルタイム検出](threat-explorer.md): 管理 **は、システムオーバーライド ソース** でフィルター処理し、**フィッシング シミュレーション** または **SecOps メールボックス** を選択できます。
- [脅威エクスプローラー/リアルタイム検出のEmail エンティティ ページ](mdo-email-entity-page.md): 管理は、**SecOps メールボックス** または [**上書き]** セクションの **[テナントオーバーライド**] の下の **フィッシング シミュレーション** によって組織のポリシーによって許可されたメッセージを表示できます。
- [脅威の保護状態レポート](view-email-security-reports.md#threat-protection-status-report): 管理は、ドロップダウン メニューの **[システムのオーバーライド] でデータを表示して** フィルター処理し、フィッシング シミュレーション システムのオーバーライドが原因で許可されたメッセージを表示することを選択できます。 SecOps メールボックスの上書きによって許可されるメッセージを表示するには、グラフの内訳 (理由別) ドロップダウン メニューで **、配信場所別****のグラフの内訳** を選択できます。
- [Microsoft Defender for Endpointでの高度なハンティング](../defender-endpoint/advanced-hunting-overview.md): フィッシング シミュレーションと SecOps メールボックス システムのオーバーライドは、EmailEvents の OrgLevelPolicy 内のオプションとして表示されます。
- [キャンペーン ビュー](campaigns.md): 管理 **は、システムオーバーライドソース** でフィルター処理し、**フィッシング シミュレーション** または **SecOps メールボックス** を選択できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[詳細配信**] ページに直接移動するには、を開きます<https://security.microsoft.com/advanceddelivery>。

- セキュリティ & コンプライアンス PowerShell に接続するには、「 [セキュリティ&コンプライアンス PowerShell への接続](/powershell/exchange/connect-to-scc-powershell)」を参照してください。

- この記事の手順を実行するには、アクセス許可を割り当てる必要があります。
  - 高度な配信ポリシーで構成された設定を作成、変更、または削除するには、**Microsoft 365 Defender ポータル** の **セキュリティ管理者** 役割グループのメンバーであり、Exchange Onlineの **組織管理** 役割グループのメンバーである必要 **があります。**
  - 高度な配信ポリシーへの読み取り専用アクセス権を持つ場合は、 **グローバル リーダー** または **セキュリティ 閲覧者** ロール グループのメンバーである必要があります。

  詳細については、[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)と[Exchange Onlineのアクセス許可に関するページを参照](/exchange/permissions-exo/permissions-exo)してください。

  > [!NOTE]
  > 対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 Defender ポータルで必要なアクセス許可 _と_、Microsoft 365 の他の機能に対するアクセス許可がユーザーに付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>Microsoft 365 Defender ポータルを使用して、高度な配信ポリシーで SecOps メールボックスを構成する

1. Microsoft 365 Defender ポータルの [ルール **] セクション** の <https://security.microsoft.com>**[Email & コラボレーション** \> **ポリシー&ルール** \> **脅威ポリシー** \> **の詳細配信**] に移動します。 **[詳細配信**] ページに直接移動するには、 <https://security.microsoft.com/advanceddelivery>.

2. [ **詳細配信** ] ページで、[ **SecOps メールボックス** ] タブが選択されていることを確認し、次のいずれかの手順を実行します。
   - [編集] アイコンをクリック ![します。](../../media/m365-cc-sc-edit-icon.png) **編集**。
   - 構成済みの SecOps メールボックスがない場合は、[ **追加**] をクリックします。

3. 開いた **[Edit SecOps mailboxes**] ポップアップで、次のいずれかの手順を実行して、SecOps メールボックスとして指定する既存のExchange Online メールボックスを入力します。
   - ボックスをクリックし、メールボックスの一覧を解決し、メールボックスを選択します。
   - ボックス内をクリックして、メールボックスの識別子 (名前、表示名、エイリアス、電子メール アドレス、アカウント名など) の入力を開始し、結果からメールボックス (表示名) を選択します。

     必要な回数だけこの手順を繰り返します。 配布グループは許可されません。

     既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

4. 完了したら、**[保存]** をクリックします。

構成した SecOps メールボックス エントリは、[ **SecOps メールボックス** ] タブに表示されます。変更を加えるには、[編集] アイコンをクリックします ![。](../../media/m365-cc-sc-edit-icon.png) タブで **編集** します。

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Microsoft 365 Defender ポータルを使用して、高度な配信ポリシーでサード パーティのフィッシング シミュレーションを構成する

1. Microsoft 365 Defender ポータルの [ルール **] セクション** の <https://security.microsoft.com>**[Email & コラボレーション** \> **ポリシー&ルール** \> **脅威ポリシー** \> **の詳細配信**] に移動します。 **[詳細配信**] ページに直接移動するには、 <https://security.microsoft.com/advanceddelivery>.

2. [ **詳細配信** ] ページで、[ **フィッシング シミュレーション** ] タブを選択し、次のいずれかの手順を実行します。
   - [編集] アイコンをクリック ![します。](../../media/m365-cc-sc-edit-icon.png) **編集**。
   - 構成済みのフィッシング シミュレーションがない場合は、[ **追加**] をクリックします。

3. 開いた **サード パーティ製のフィッシング シミュレーション ポップアップを編集** するで、次の設定を構成します。

   - **ドメイン**: この設定を展開し、ボックスをクリックして値を入力し、Enter キーを押すか、ボックスの下に表示される値を選択して、少なくとも 1 つの電子メール アドレス ドメイン (contoso.com など) を入力します。 必要な回数だけこの手順を繰り返します。 最大 20 個のエントリを追加できます。

     > [!NOTE]
     > フィッシング シミュレーション ベンダーによって指定された、メッセージの SMTP 送信 **または** DomainKeys 識別メール (DKIM) ドメインで使用されるアドレス (MAIL **FROM** アドレス、P1 送信者、エンベロープ送信者とも呼ばれます) の`5321.MailFrom`ドメインを使用します。

   - **IP の送信**: この設定を展開し、ボックスをクリックして値を入力し、Enter キーを押すか、ボックスの下に表示される値を選択して、有効な IPv4 アドレスを少なくとも 1 つ入力します。 必要な回数だけこの手順を繰り返します。 最大 10 個のエントリを追加できます。 有効な値は次のとおりです。
     - 単一 IP: たとえば、192.168.1.1 です。
     - IP 範囲: たとえば、192.168.0.1-192.168.0.254 です。
     - CIDR IP: たとえば、192.168.0.1/25 です。

   - **許可するシミュレーション URL**: この設定を展開し、必要に応じて、ボックス内をクリックして値を入力し、Enter キーを押すか、ボックスの下に表示される値を選択して、ブロックまたは爆発してはならないフィッシング シミュレーション キャンペーンの一部である特定の URL を入力します。 最大 10 個のエントリを追加できます。 URL 構文の形式については、 [テナント許可/ブロック リストの URL 構文に関するページ](tenant-allow-block-list.md#url-syntax-for-the-tenant-allowblock-list)を参照してください。 これらの URL はクリック時にラップされますが、ブロックされません。

   既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

   > [!NOTE]
   > Advanced Delivery でサード パーティのフィッシング シミュレーションを構成するには、次の情報を指定する必要があります。
   >
   > - 次のいずれかのソースから少なくとも 1 つの **ドメイン** :
   >   - `5321.MailFrom`アドレス (MAIL FROM アドレス、P1 送信者、封筒送信者とも呼ばれます)。
   >   - DKIM ドメイン。
   > - 少なくとも 1 つの **送信 IP**。
   >
   > 必要に応じて **シミュレーション URL を含め、シミュレーション** メッセージ内の URL がブロックされないようにすることができます。
   > フィールドごとに最大 10 個のエントリを指定できます。
   > 少なくとも 1 つの **ドメイン** と 1 つの **送信 IP** に一致する必要がありますが、値間の関連付けは維持されません。

4. 完了したら、次のいずれかの手順を実行します。
   - **初回:** [ **追加]** をクリックし、[ **閉じる**] をクリックします。
   - **既存のものを編集する**: [ **保存]** をクリックし、[ **閉じる**] をクリックします。

構成したサード パーティ製のフィッシング シミュレーション エントリは、[ **フィッシング シミュレーション** ] タブに表示されます。変更を加えるには、[編集] アイコンをクリックします ![。](../../media/m365-cc-sc-edit-icon.png) タブで **編集** します。

## <a name="additional-scenarios-that-require-filtering-bypass"></a>フィルター処理のバイパスが必要なその他のシナリオ

高度な配信ポリシーで役立つ 2 つのシナリオに加えて、フィルター処理をバイパスする必要がある他のシナリオもあります。

- **サード パーティのフィルター**: ドメインの MX レコードがOffice 365を指 _していない_ 場合 (メッセージは最初に別の場所にルーティングされます)、[既定ではセキュリティで保護](secure-by-default.md)_されません_。 保護を追加する場合は、コネクタの拡張フィルター処理 ( _リストのスキップ_ とも呼ばれます) を有効にする必要があります。 詳細については、「Exchange Onlineを[使用したサード パーティのクラウド サービスを使用したメール フローの管理](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud)」を参照してください。 コネクタの拡張フィルター処理が不要な場合は、メール フロー ルール (トランスポート ルールとも呼ばれます) を使用して、サード パーティのフィルター処理によって既に評価されているメッセージの Microsoft フィルター処理をバイパスします。 詳細については、「 [メール フロー ルールを使用してメッセージに SCL を設定する](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)」を参照してください。

- **レビュー中の誤検知**: [管理者の提出](admin-submission.md) を通じて Microsoft によって分析されている特定のメッセージを一時的に許可し、不適切とマークされている既知の良好なメッセージを Microsoft に報告することができます (誤検知)。 すべてのオーバーライドと同様に、これらの許容量は一時的な値であることを _**強くお勧めします**_ 。

## <a name="security--compliance-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a>高度な配信ポリシーの SecOps メールボックスのセキュリティ & コンプライアンス PowerShell の手順

Security & Compliance PowerShell では、高度な配信ポリシーの SecOps メールボックスの基本的な要素は次のとおりです。

- **SecOps オーバーライド ポリシー**: **-SecOpsOverridePolicy コマンドレットによって\*** 制御されます。
- **SecOps オーバーライド規則**: **-SecOpsOverrideRule コマンドレットによって\*** 制御されます。

この動作の結果は次のとおりです。

- 最初にポリシーを作成し、ルールが適用されるポリシーを識別するルールを作成します。
- PowerShell からポリシーを削除すると、対応するルールも削除されます。
- PowerShell からルールを削除しても、対応するポリシーは削除されません。 対応するポリシーを手動で削除する必要があります。

### <a name="use-powershell-to-configure-secops-mailboxes"></a>PowerShell を使用して SecOps メールボックスを構成する

PowerShell の高度な配信ポリシーで SecOps メールボックスを構成するには、次の 2 つの手順を実行します。

1. SecOps オーバーライド ポリシーを作成します。
2. ルールが適用されるポリシーを指定する SecOps オーバーライド 規則を作成します。

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a>手順 1: PowerShell を使用して SecOps オーバーライド ポリシーを作成する

SecOps オーバーライド ポリシーを作成するには、次の構文を使用します。

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

> [!NOTE]
> 指定した名前の値に関係なく、ポリシー名は _SecOpsOverridePolicy_ になるため、その値を使用することもできます。

この例では、SecOps メールボックス ポリシーを作成します。

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo secops@contoso.com
```

構文とパラメーターの詳細については、「 [New-SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy)」を参照してください。

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a>手順 2: PowerShell を使用して SecOps オーバーライド規則を作成する

この例では、指定した設定で SecOps メールボックス規則を作成します。

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

> [!NOTE]
> 指定した名前の値に関係なく、ルール名は一意の GUID 値である _SecOpsOverrideRule_\<GUID\> \<GUID\> になります (たとえば、6fed4b63-3563-495d-a481-b24a311f8329)。

構文とパラメーターの詳細については、「 [New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule)」を参照してください。

### <a name="use-powershell-to-view-the-secops-override-policy"></a>PowerShell を使用して SecOps オーバーライド ポリシーを表示する

この例では、1 つだけの SecOps メールボックス ポリシーに関する詳細情報を返します。

```powershell
Get-SecOpsOverridePolicy
```

構文とパラメーターの詳細については、「 [Get-SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy)」を参照してください。

### <a name="use-powershell-to-view-secops-override-rules"></a>PowerShell を使用して SecOps オーバーライド規則を表示する

この例では、SecOps オーバーライド 規則に関する詳細情報を返します。

```powershell
Get-SecOpsOverrideRule
```

前のコマンドは 1 つのルールのみを返す必要がありますが、削除を保留しているすべてのルールも結果に含まれる可能性があります。

この例では、有効なルール (1 つ) と無効なルールを識別します。

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

無効な規則を特定したら、[この記事で後述](#use-powershell-to-remove-secops-override-rules)するように **Remove-SecOpsOverrideRule** コマンドレットを使用して削除できます。

構文とパラメーターの詳細については、「 [Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)」を参照してください。

### <a name="use-powershell-to-modify-the-secops-override-policy"></a>PowerShell を使用して SecOps オーバーライド ポリシーを変更する

SecOps オーバーライド ポリシーを変更するには、次の構文を使用します。

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

この例では、SecOps オーバーライド ポリシーに追加 `secops2@contoso.com` します。

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

> [!NOTE]
> 関連付けられた有効な SecOps オーバーライド規則が存在する場合は、ルール内の電子メール アドレスも更新されます。

構文とパラメーターの詳細については、「 [Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy)」を参照してください。

### <a name="use-powershell-to-modify-a-secops-override-rule"></a>PowerShell を使用して SecOps オーバーライド規則を変更する

**Set-SecOpsOverrideRule** コマンドレットは、SecOps オーバーライド規則の電子メール アドレスを変更しません。 SecOps オーバーライド規則の電子メール アドレスを変更するには、 **Set-SecOpsOverridePolicy** コマンドレットを使用します。

構文とパラメーターの詳細については、「 [Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule)」を参照してください。

### <a name="use-powershell-to-remove-the-secops-override-policy"></a>PowerShell を使用して SecOps オーバーライド ポリシーを削除する

この例では、SecOps メールボックス ポリシーと対応するルールを削除します。

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

構文とパラメーターの詳細については、「 [Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy)」を参照してください。

### <a name="use-powershell-to-remove-secops-override-rules"></a>PowerShell を使用して SecOps オーバーライド規則を削除する

SecOps オーバーライド規則を削除するには、次の構文を使用します。

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

この例では、指定した SecOps オーバーライド規則を削除します。

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

構文とパラメーターの詳細については、「 [Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule)」を参照してください。

## <a name="security--compliance-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>高度な配信ポリシーでのサード パーティ製フィッシング シミュレーションのセキュリティ&コンプライアンス PowerShell の手順

Security & Compliance PowerShell では、高度な配信ポリシーのサード パーティフィッシング シミュレーションの基本的な要素は次のとおりです。

- **フィッシング シミュレーションオーバーライド ポリシー**: **-PhishSimOverridePolicy コマンドレットによって\*** 制御されます。
- **フィッシング シミュレーションオーバーライド規則**: **-PhishSimOverrideRule コマンドレットによって\*** 制御されます。
- **許可された (ブロック解除された) フィッシング シミュレーション URL**: **-TenantAllowBlockListItems コマンドレットによって\*** 制御されます。

この動作の結果は次のとおりです。

- 最初にポリシーを作成し、ルールが適用されるポリシーを識別するルールを作成します。
- ポリシーとルールの設定は個別に変更します。
- PowerShell からポリシーを削除すると、対応するルールも削除されます。
- PowerShell からルールを削除しても、対応するポリシーは削除されません。 対応するポリシーを手動で削除する必要があります。

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a>PowerShell を使用してサードパーティのフィッシング シミュレーションを構成する

PowerShell でサード パーティのフィッシング シミュレーションを構成することは、次の複数ステップのプロセスです。

1. フィッシング シミュレーションオーバーライド ポリシーを作成します。
2. 次を指定するフィッシング シミュレーションオーバーライドルールを作成します。
   - ルールが適用されるポリシー。
   - フィッシング シミュレーション メッセージの送信元 IP アドレス。
3. 必要に応じて、許可する必要があるフィッシング シミュレーション URL を識別します (つまり、ブロックまたはスキャンされません)。

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a>手順 1: PowerShell を使用してフィッシング シミュレーションオーバーライド ポリシーを作成する

この例では、フィッシング シミュレーションオーバーライド ポリシーを作成します。

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

**注**: 指定した名前の値に関係なく、ポリシー名は _PhishSimOverridePolicy_ になるため、その値を使用することもできます。

構文とパラメーターの詳細については、「 [New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy)」を参照してください。

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a>手順 2: PowerShell を使用してフィッシング シミュレーションオーバーライド ルールを作成する

次の構文を使用してください。

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -Domains <Domain1>,<Domain2>,...<Domain10> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntry10>
```

指定した名前の値に関係なく、ルール名は一意の GUID 値である \<GUID\> _PhishSimOverrideRule_\<GUID\> になります (たとえば、a0eae53e-d755-4a42-9320-b9c6b55c5011)。

有効な IP アドレス エントリは、次のいずれかの値です。

- 単一 IP: たとえば、192.168.1.1 です。
- IP 範囲: たとえば、192.168.0.1-192.168.0.254 です。
- CIDR IP: たとえば、192.168.0.1/25 です。

この例では、指定した設定を使用してフィッシング シミュレーションオーバーライドルールを作成します。

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -Domains fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

構文とパラメーターの詳細については、「 [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule)」を参照してください。

#### <a name="step-3-optional-use-powershell-to-identify-the-phishing-simulation-urls-to-allow"></a>手順 3: (省略可能) PowerShell を使用して、許可するフィッシング シミュレーション URL を識別する

次の構文を使用してください。

```powershell
New-TenantAllowBlockListItems -Allow -ListType Url -ListSubType AdvancedDelivery -Entries "<URL1>","<URL2>",..."<URL10>" <[-NoExpiration] | [-ExpirationDate <DateTime>]>
```

URL 構文の詳細については、 [テナント許可/ブロック リストの URL 構文に関するページ](tenant-allow-block-list.md#url-syntax-for-the-tenant-allowblock-list)を参照してください。

この例では、指定したサード パーティ製フィッシング シミュレーション URL の URL 許可エントリを有効期限なしで追加します。

```powershell
New-TenantAllowBlockListItems -Allow -ListType Url -ListSubType AdvancedDelivery -Entries *.fabrikam.com -NoExpiration
```

構文とパラメーターの詳細については、「 [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems)」を参照してください。

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a>PowerShell を使用してフィッシング シミュレーションオーバーライド ポリシーを表示する

この例では、フィッシング シミュレーションオーバーライド ポリシーに関する詳細情報のみを返します。

```powershell
Get-PhishSimOverridePolicy
```

構文とパラメーターの詳細については、「 [Get-PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy)」を参照してください。

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a>PowerShell を使用してフィッシング シミュレーションオーバーライド ルールを表示する

この例では、フィッシング シミュレーションオーバーライド ルールに関する詳細情報を返します。

```powershell
Get-PhishSimOverrideRule
```

前のコマンドは 1 つのルールのみを返す必要がありますが、削除を保留しているすべてのルールも結果に含まれる可能性があります。

この例では、有効なルール (1 つ) と無効なルールを識別します。

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

無効なルールを特定したら、[この記事で後述](#use-powershell-to-remove-phishing-simulation-override-rules)するように **Remove-PhishSimOverrideRule** コマンドレットを使用して削除できます。

構文とパラメーターの詳細については、「 [Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule)」を参照してください。

### <a name="use-powershell-to-view-the-allowed-phishing-simulation-url-entries"></a>PowerShell を使用して、許可されたフィッシング シミュレーション URL エントリを表示する

許可されているフィッシング シミュレーション URL を表示するには、次のコマンドを実行します。

```powershell
Get-TenantAllowBlockListItems -ListType Url -ListSubType AdvancedDelivery
```

構文とパラメーターの詳細については、「 [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)」を参照してください。

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a>PowerShell を使用してフィッシング シミュレーションオーバーライド ポリシーを変更する

フィッシング シミュレーションオーバーライド ポリシーを変更するには、次の構文を使用します。

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

この例では、フィッシング シミュレーションオーバーライド ポリシーを無効にします。

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

構文とパラメーターの詳細については、「 [Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy)」を参照してください。

### <a name="use-powershell-to-modify-phishing-simulation-override-rules"></a>PowerShell を使用してフィッシング シミュレーションオーバーライドルールを変更する

フィッシング シミュレーションオーバーライド規則を変更するには、次の構文を使用します。

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

この例では、次の設定を使用して、指定したフィッシング シミュレーションオーバーライドルールを変更します。

- ドメイン エントリを blueyonderairlines.com 追加します。
- IP アドレス エントリ 192.168.1.55 を削除します。

これらの変更は、既存のエントリには影響しません。

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

構文とパラメーターの詳細については、「 [Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule)」を参照してください。

### <a name="use-powershell-to-modify-the-allowed-phishing-simulation-url-entries"></a>PowerShell を使用して、許可されたフィッシング シミュレーション URL エントリを変更する

URL 値を直接変更することはできません。 この記事で説明されているように [、既存の URL エントリを削除](#use-powershell-to-remove-the-allowed-phishing-simulation-url-entries) し [、新しい URL エントリを追加](#step-3-optional-use-powershell-to-identify-the-phishing-simulation-urls-to-allow) できます。

許可されているフィッシング シミュレーション URL エントリの他のプロパティ (有効期限やコメントなど) を変更するには、次の構文を使用します。

```powershell
Set-TenantAllowBlockListItems <-Entries "<URL1>","<URL2>",..."<URLN>" | -Ids <Identity>> -ListType URL -ListSubType AdvancedDelivery <[-NoExpiration] | [-ExpirationDate <DateTime>]> [-Notes <String>]
```

変更するエントリは、その URL 値 ( _Entrys_ パラメーター) または **Get-TenantAllowBlockListItems** コマンドレットの出力 ( _Ids_ パラメーター) の ID 値によって識別します。

この例では、指定したエントリの有効期限を変更しました。

```powershell
Set-TenantAllowBlockListItems -ListType Url -ListSubType AdvancedDelivery -Entries "*.fabrikam.com" -ExpirationDate 9/11/2021
```

構文とパラメーターの詳細については、「 [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems)」を参照してください。

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a>PowerShell を使用してフィッシング シミュレーションオーバーライド ポリシーを削除する

この例では、フィッシング シミュレーションオーバーライド ポリシーと対応するルールを削除します。

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

構文とパラメーターの詳細については、「 [Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy)」を参照してください。

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a>PowerShell を使用してフィッシング シミュレーションオーバーライドルールを削除する

フィッシング シミュレーションオーバーライド規則を削除するには、次の構文を使用します。

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

この例では、指定したフィッシング シミュレーションオーバーライド ルールを削除します。

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

構文とパラメーターの詳細については、「 [Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule)」を参照してください。

### <a name="use-powershell-to-remove-the-allowed-phishing-simulation-url-entries"></a>PowerShell を使用して、許可されたフィッシング シミュレーション URL エントリを削除する

既存のフィッシング シミュレーション URL エントリを削除するには、次の構文を使用します。

```powershell
Remove-TenantAllowBlockListItems <-Entries "<URL1>","<URL2>",..."<URLN>" | -Ids <Identity>> -ListType URL -ListSubType AdvancedDelivery
```

変更するエントリは、その URL 値 ( _Entrys_ パラメーター) または **Get-TenantAllowBlockListItems** コマンドレットの出力 ( _Ids_ パラメーター) の ID 値によって識別します。

この例では、指定したエントリの有効期限を変更しました。

```powershell
Remove-TenantAllowBlockListItems -ListType Url -ListSubType AdvancedDelivery -Entries "*.fabrikam.com" -ExpirationDate 9/11/2021
```

構文とパラメーターの詳細については、「 [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems)」を参照してください。
