---
title: スプーフィング インテリジェンス分析
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) でスプーフィング インテリジェンスの分析情報について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fc09bb008586b26649e31f409fa3be8114c6d2b6
ms.sourcegitcommit: 38a18b0195d99222c2c6da0c80838d24b5f66b97
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2022
ms.locfileid: "65772108"
---
# <a name="spoof-intelligence-insight-in-eop"></a>詳細については、「EOP のスプーフィング インテリジェンス分析」を参照してください。

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Onlineまたはスタンドアロン Exchange Online Protection (EOP) 組織にメールボックスを含むMicrosoft 365組織では、Exchange Onlineメールボックスがない場合、受信電子メール メッセージはスプーフィングから自動的に保護されます。 EOP では、フィッシングに対する組織全体の防御の一環として **、スプーフィング インテリジェンス** が使用されます。 詳細については、「 [EOP でのスプーフィング対策保護](anti-spoofing-protection.md)」を参照してください。

送信者が電子メール アドレスをスプーフィングすると、組織のドメインの 1 つのユーザー、または組織に電子メールを送信する外部ドメイン内のユーザーのように見えます。 スパムやフィッシングメールを送信するために送信者をスプーフィングする攻撃者は、ブロックする必要があります。 ただし、正当な送信者がスプーフィングを行うシナリオがあります。 例として以下のようなものがあります。

- 内部ドメインをスプーフィングするための正当なシナリオ:
  - サードパーティの送信者は、ドメインを使用して、会社の投票のために自分の従業員に一括メールを送信します。
  - 外部企業は、お客様に代わって広告または製品の更新プログラムを生成して送信します。
  - アシスタントは、組織内の別のユーザーの電子メールを定期的に送信する必要があります。
  - 内部アプリケーションは、電子メール通知を送信します。

- 外部ドメインをスプーフィングするための正当なシナリオ:
  - 送信者はメーリング リスト (ディスカッション リストとも呼ばれます) にあり、メーリング リストは元の送信者からメーリング リストのすべての参加者にメールを中継します。
  - 外部企業は、別の会社 (自動化されたレポートやサービスとしてのソフトウェア会社など) に代わって電子メールを送信します。

Microsoft 365 Defender ポータルで **スプーフィング インテリジェンス 分析情報** を使用すると、正当に認証されていないメール (SPF、DKIM、DMARC チェックを通過しないドメインからのメッセージ) を正当に送信しているスプーフィングされた送信者をすばやく特定し、それらの送信者を手動で許可することができます。

既知の送信者が既知の場所からスプーフィングされたメッセージを送信できるようにすることで、誤検知 (不適切とマークされた良好なメール) を減らすことができます。 許可されたスプーフィングされた送信者を監視することで、安全でないメッセージが組織に届くのを防ぐために、セキュリティの追加レイヤーを提供します。

同様に、スプーフィング インテリジェンスによって許可されたスプーフィングされた送信者を確認し、それらの送信者をスプーフィング インテリジェンスの分析情報から手動でブロックできます。

この記事の残りの部分では、Microsoft 365 Defender ポータルと PowerShell でスプーフィング インテリジェンス分析情報を使用する方法について説明します (Exchange Onlineのメールボックスを持つMicrosoft 365組織の PowerShell をExchange Onlineし、スタンドアロンの EOP PowerShell を使用しない組織向けExchange Online メールボックス)。

> [!NOTE]
>
> - スプーフィング インテリジェンスによって検出されたスプーフィングされた送信者のみが、スプーフィング インテリジェンス分析情報に表示されます。 分析情報の許可またはブロックの判定をオーバーライドすると、スプーフィングされた送信者は、テナント許可/ブロックリストの [ **スプーフィング** ] タブにのみ表示される手動の許可エントリまたはブロック エントリになります。 スプーフィングされた送信者がスプーフィング インテリジェンスによって検出される前に、許可エントリまたはブロック エントリを手動で作成することもできます。 詳細については、「[EOP でテナント許可/ブロック リストを管理する](tenant-allow-block-list.md)」を参照してください。
>
> - スプーフィング インテリジェンス分析情報とテナント許可/ブロックの一覧の [ **スプーフィング** ] タブは、セキュリティ & コンプライアンス センターのスパム対策ポリシー ページで使用できたスプーフィング インテリジェンス ポリシーの機能を置き換えます。
>
>- スプーフィング インテリジェンス分析情報には、7 日間分のデータが表示されます。 **Get-SpoofIntelligenceInsight** コマンドレットには、30 日分のデータが表示されます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[テナントの許可/ブロック一覧**] ページの [**スプーフィング**] タブに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList?viewid=SpoofItem>. **スプーフィング インテリジェンス分析情報** ページに直接移動するには、<https://security.microsoft.com/spoofintelligence>.

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - スプーフィング インテリジェンス ポリシーを変更したり、スプーフィング インテリジェンスを有効または無効にするには、 
    -   **組織の管理**
    -   **セキュリティ管理者**<u>と</u>**表示専用構成** または **表示専用組織管理**。
  - スプーフィング インテリジェンス ポリシーへの読み取り専用アクセスの場合は、 **グローバル リーダー** または **セキュリティ 閲覧者** ロール グループのメンバーである必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  > [!NOTE]
  >
  > - Microsoft 365 管理センターで、対応する Azure Active Directory のロールにユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。詳しくは、「[管理者のロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- EOP とMicrosoft Defender for Office 365のフィッシング対策ポリシーでスプーフィング インテリジェンスを有効または無効にします。 スプーフィング インテリジェンスは既定で有効になっています。 詳細については、「[EOP でフィッシング対策ポリシーを構成する](configure-anti-phishing-policies-eop.md)」または「[Microsoft Defender for Office 365でフィッシング対策ポリシーを構成する](configure-mdo-anti-phishing-policies.md)」を参照してください。

- スプーフィング インテリジェンスの推奨設定については、「 [EOP フィッシング対策ポリシーの設定](recommended-settings-for-eop-and-office365-atp.md#eop-anti-phishing-policy-settings)」を参照してください。

## <a name="open-the-spoof-intelligence-insight-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルでスプーフィング インテリジェンス分析情報を開く

1. Microsoft 365 Defender ポータルの [ルール **] セクション** の <https://security.microsoft.com>**[電子メール & コラボレーション** \> **ポリシー&ルール** \> **脅威ポリシー** \> **テナント許可/ブロック リスト**] に移動します。 **[テナントの許可/ブロック一覧**] ページの [**スプーフィング**] タブに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList?viewid=SpoofItem>.

2. [ **テナントの許可/ブロック リスト]** ページで、スプーフィング インテリジェンスの分析情報は次のようになります。

   :::image type="content" source="../../media/m365-sc-spoof-intelligence-insight.png" alt-text="フィッシング対策ポリシー ページのスプーフィング インテリジェンス分析情報" lightbox="../../media/m365-sc-spoof-intelligence-insight.png":::

   分析情報には、次の 2 つのモードがあります。

   - **分析情報モード**: スプーフィング インテリジェンスが有効になっている場合、過去 7 日間にスプーフィング インテリジェンスによって検出されたメッセージの数が分析情報に表示されます。
   - **モードの場合** の動作: スプーフィング インテリジェンスが無効になっている場合、過去 7 日間にスプーフィング インテリジェンスによって検出 *されたメッセージの* 数が分析情報に表示されます。

スプーフィング インテリジェンス検出に関する情報を表示するには、 **スプーフィング インテリジェンス分析情報で [スプーフィング アクティビティの表示** ] をクリックします。

### <a name="view-information-about-spoofed-messages"></a>スプーフィングされたメッセージに関する情報を表示する

> [!NOTE]
> このページには、スプーフィング インテリジェンスによって検出されたスプーフィングされた送信者のみが表示されることを忘れないでください。 分析情報の許可またはブロックの判定をオーバーライドすると、スプーフィングされた送信者は、テナント許可/ブロックリストの [ **スプーフィング** ] タブにのみ表示される手動の許可エントリまたはブロック エントリになります。

**スプーフィング インテリジェンス 分析情報** で [**スプーフィング アクティビティの表示**] をクリックした後に表示される [スプーフィング インテリジェンス分析情報] ページには、次の情報が含まれています。

- **スプーフィングされたユーザー**: メール クライアントの [**送信元**] ボックスに表示されるスプーフィングされたユーザーの **ドメイン**。 差出人アドレスは、アドレスとも `5322.From` 呼ばれます。
- **インフラストラクチャの送信**: _インフラストラクチャ_ とも呼ばれます。 送信インフラストラクチャは、次のいずれかの値になります。
  - 送信元電子メール サーバーの IP アドレスの逆引き DNS 参照 (PTR レコード) で見つかったドメイン。
  - 送信元 IP アドレスに PTR レコードがない場合、送信インフラストラクチャは /24 (たとえば、192.168.100.100/24) として \<source IP\>識別されます。
  - 検証済みの DKIM ドメイン。
- **メッセージ数**: 過去 7 日以内に、スプーフィングされたドメイン _と_ 組織への送信インフラストラクチャの組み合わせからのメッセージの数。
- **最終更新日**: スプーフィングされたドメインを含む送信インフラストラクチャからメッセージを受信した最後の日付。
- **スプーフィングの種類**: 次のいずれかの値。
  - **内部**: スプーフィングされた送信者は、組織に属するドメイン ( [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) にあります。
  - **外部**: スプーフィングされた送信者は外部ドメインにあります。
- **アクション**: この値は **[許可]** または **[ブロック] です**。
  - **許可**: ドメインで、 [SPF](how-office-365-uses-spf-to-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)、 [DMARC](use-dmarc-to-validate-email.md) の明示的な電子メール認証チェックに失敗しました。 ただし、ドメインは暗黙的な電子メール認証チェック ([複合認証](email-validation-and-authentication.md#composite-authentication)) に合格しました。 その結果、メッセージに対してスプーフィング対策アクションは実行されませんでした。
  - **ブロック:** スプーフィングされたドメイン _と_ 送信インフラストラクチャの組み合わせからのメッセージは、スプーフィング インテリジェンスによって不適切とマークされます。 スプーフィングされたメッセージに対して実行されるアクションは、既定のフィッシング対策ポリシーまたはカスタムフィッシング対策ポリシー (既定値は迷惑 **メール フォルダーへのメッセージの移動**) によって制御されます。 詳細については、「[Microsoft Defender for Office 365でのフィッシング対策ポリシーの構成](configure-mdo-anti-phishing-policies.md)」を参照してください。

選択した列見出しをクリックすると、結果を並べ替えることができます。

結果をフィルター処理するには、次のオプションがあります。

- [ **フィルター** ] ボタンをクリックします。 表示される **[フィルター** ] ポップアップで、次の方法で結果をフィルター処理できます。
  - **スプーフィングの種類**
  - **操作**
- **検索** ボックスを使用して、スプーフィングされたドメイン値のコンマ区切りリストを入力するか、インフラストラクチャ値を送信して結果をフィルター処理します。

### <a name="view-details-about-spoofed-messages"></a>スプーフィングされたメッセージの詳細を表示する

一覧からエントリを選択すると、次の情報と機能を含む詳細ポップアップが表示されます。

- **スプーフィングまたはスプーフィング****のブロックを** 許可する: これらの値のいずれかを選択して、元のスプーフィング インテリジェンスの判定をオーバーライドし、スプーフィングインテリジェンス分析情報からスプーフィングの許可エントリまたはブロック エントリとしてテナント許可/ブロック リストにエントリを移動します。
- これをキャッチした理由。
- 実行する必要がある操作。
- メインスプーフィング インテリジェンス ページの同じ情報のほとんどを含むドメインの概要。
- 送信者に関する WhoIs データ。
- [脅威エクスプローラー](threat-explorer.md)を開き、[Microsoft Defender for Office 365での **フィッシング** の表示] で送信者に関する追加情報を **表示**\>するためのリンク。
- 同じ送信者からテナントで見た同様のメッセージ。

### <a name="about-allowed-spoofed-senders"></a>許可されたスプーフィング送信者について

スプーフィング インテリジェンス 分析情報で許可されたスプーフィングされた送信者、または手動で [スプーフィングを許可する] に変更したブロックされた **スプーフィン** グされた送信者は、スプーフィングされたドメイン _と_ 送信インフラストラクチャの組み合わせからのメッセージのみを許可します。 スプーフィングされたドメインからの電子メールを任意のソースから許可したり、ドメインの送信インフラストラクチャからの電子メールを許可したりすることはありません。

たとえば、次のスプーフィングされた送信者はスプーフィングを許可されます。

- **ドメイン**: gmail.com
- **インフラストラクチャ**: tms.mx.com

スプーフィングを許可されるのは、そのドメインと送信インフラストラクチャのペアからのメールのみです。 gmail.com スプーフィングを試みる他の送信者は、自動的には許可されません。 tms.mx.com から送信された他のドメインの送信者からのメッセージは、スプーフィング インテリジェンスによって引き続きチェックされ、ブロックされる可能性があります。

## <a name="use-the-spoof-intelligence-insight-in-exchange-online-powershell-or-standalone-eop-powershell"></a>PowerShell またはスタンドアロンの EOP PowerShell Exchange Onlineスプーフィング インテリジェンス分析情報を使用する

PowerShell では、 **Get-SpoofIntelligenceInsight** コマンドレットを使用して、スプーフィング インテリジェンスによって検出された、許可されたスプーフィングされた送信者とブロックされたスプーフィングされた送信者を **表示** します。 スプーフィングされた送信者を手動で許可またはブロックするには、 **New-TenantAllowBlockListSpoofItems** コマンドレットを使用する必要があります。 詳細については、「 [PowerShell を使用してテナント許可/ブロック リストにスプーフィングされた送信者エントリを管理する」を参照してください](tenant-allow-block-list.md)。

スプーフィング インテリジェンス分析情報の情報を表示するには、次のコマンドを実行します。

```powershell
Get-SpoofIntelligenceInsight
```

構文とパラメーターの詳細については、「 [Get-SpoofIntelligenceInsight](/powershell/module/exchange/get-spoofintelligenceinsight)」を参照してください。

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>スプーフィングとフィッシングを管理するその他の方法

スプーフィングとフィッシングの保護に勤勉に取り組む。 ドメインをスプーフィングしている送信者を確認し、組織に損害を与えないようにする関連する方法を次に示します。

- **スプーフィング メール レポート** を確認します。 このレポートは、多くの場合、スプーフィングされた送信者を表示して管理するのに役立ちます。 詳細については、「 [スプーフィング検出レポート」を](view-email-security-reports.md#spoof-detections-report)参照してください。

- Sender Policy Framework (SPF) の構成を確認します。 SPF の概要と SPF を迅速に構成する方法については、「[スプーフィングを防止するために Microsoft 365 で SPF を設定する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)」を参照してください。 Office 365 における SPF の使用方法についての詳細や、ハイブリッド展開などの非標準の展開のトラブルシューティングについては、「[How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)」をご確認ください。

- DomainKeys 識別メール (DKIM) の構成を確認します。 SPF と DMARC に加えて DKIM を使用して、攻撃者がドメインから送信されたようなメッセージを送信できないようにする必要があります。 DKIM では、電子メール メッセージのメッセージ ヘッダー内にデジタル署名を追加することができます。 詳細については、「[DKIM を使用して、Office 365でカスタム ドメインから送信された送信メールを検証する](use-dkim-to-validate-outbound-email.md)」を参照してください。

- ドメイン ベースのメッセージ認証、レポート、および準拠 (DMARC) の構成を確認します。 SPF および DKIM と共に DMARC を実装すると、メールのスプーフィングやフィッシングに対抗する追加の保護が得られます。 DMARC は、電子メールを受信するシステムが、ドメインから送信された SPF チェックまたは DKIM チェックに失敗したメッセージに対して、どのように対応するかを判断する際に役に立ちます。 詳細については、「[DMARC を使用してOffice 365で電子メールを検証する](use-dmarc-to-validate-email.md)」を参照してください。
