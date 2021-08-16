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
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、スプーフィング インテリジェンスの分析情報について、Exchange Online Protection (EOP) で学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2f17ac22a85182356ac58952b1d381fc6a98451e
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "58258546"
---
# <a name="spoof-intelligence-insight-in-eop"></a>EOP でのスプーフィング インテリジェンスの分析情報

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> この記事で説明する機能はプレビューで、変更される可能性があります。一部の組織では利用できません。 この記事で説明する機能が組織に存在しない場合は [、「EOP](walkthrough-spoof-intelligence-insight.md)のスプーフィング インテリジェンス ポリシーとスプーフィング インテリジェンスインサイトを使用してスプーフィング送信者を管理する」で、以前のスプーフィング管理エクスペリエンスを参照してください。

Microsoft 365 Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない組織では、受信電子メール メッセージはスプーフィングから自動的に保護されます。 EOP は、 **フィッシングに** 対する組織の全体的な防御の一環としてスプーフィング インテリジェンスを使用します。 詳細については、「EOP でのスプーフィング防止 [保護」を参照してください](anti-spoofing-protection.md)。

送信者が電子メール アドレスをスプーフィングすると、その送信者は組織のドメインの 1 つのユーザー、または組織に電子メールを送信する外部ドメインのユーザーのように見える。 送信者をスプーフィングしてスパムメールやフィッシングメールを送信する攻撃者をブロックする必要があります。 しかし、正当な送信者がスプーフィングを行うシナリオがあります。 例:

- 内部ドメインをスプーフィングする正当なシナリオ:
  - サードパーティの送信者は、ドメインを使用して、会社の投票のために自分の従業員にバルク メールを送信します。
  - 外部企業は、お客様に代わって広告や製品の更新プログラムを生成して送信します。
  - アシスタントは、組織内の別のユーザーのメールを定期的に送信する必要があります。
  - 内部アプリケーションが電子メール通知を送信します。

- 外部ドメインをスプーフィングする正当なシナリオ:
  - 送信者はメーリングリスト (ディスカッション リストとも呼ばれる) に登録され、メーリングリストは元の送信者からメーリングリストのすべての参加者にメールを中継します。
  - 外部企業は、別の会社に代わって電子メールを送信します (たとえば、自動レポートやサービスとしてのソフトウェア会社など)。

Microsoft 365 Defender ポータルのスプーフィング インテリジェンスインサイトを使用すると、正当に認証されていない電子メール (SPF、DKIM、または DMARC チェックに合格しないドメインからのメッセージ) をスプーフィングされた送信者をすばやく識別し、それらの送信者を手動で許可できます。

既知の送信者が既知の場所からスプーフィングされたメッセージを送信できるようにすることで、誤検知を減らします (良い電子メールは悪いとマークされています)。 許可されたスプーフィングされた送信者を監視することで、セキュリティの層を追加して、安全でないメッセージが組織に到着することを防止します。

同様に、スプーフィング インテリジェンスによって許可されたスプーフィングされた送信者を確認し、スプーフィング インテリジェンスの分析情報からそれらの送信者を手動でブロックできます。

この記事の残りの部分では、Microsoft 365 Defender ポータルと PowerShell (Exchange Online のメールボックスを持つ Microsoft 365 組織の場合は Exchange Online PowerShell、Exchange Online メールボックスのない組織ではスタンドアロンの EOP PowerShell) でスプーフィング インテリジェンスインサイトを使用する方法について説明します。

> [!NOTE]
>
> - スプーフィング インテリジェンスによって検出されたスプーフィングされた送信者だけがスプーフィング インテリジェンスの分析情報に表示されます。 インサイトで許可またはブロックの評決を上書きすると、スプーフィングされた送信者は、テナント許可/ブロック一覧の [スプーフィング] タブにのみ表示される手動の許可またはブロック エントリになります。 スプーフィング インテリジェンスによって検出される前に、スプーフィングされた送信者の許可エントリまたはブロック エントリを手動で作成することもできます。 詳細については、「[EOP でテナント許可/ブロック リストを管理する](tenant-allow-block-list.md)」を参照してください。
>
> - [テナントの許可/ブロック] リストのスプーフィング インテリジェンスインサイトと [スプーフィング] タブは、セキュリティ & コンプライアンス センターのスパム対策ポリシー ページで使用できるスプーフィング インテリジェンス ポリシーの機能を置き換えます。
>
>- スプーフィング インテリジェンスの分析情報には、7 日間分のデータが表示されます。 **Get-SpoofIntelligenceInsight** コマンドレットには、30 日分のデータが表示されます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com/> で Microsoft 365 Defender ポータルを開きます。 [テナントの許可/ブロック **リスト]** ページの [スプーフィング] タブに直接移動するには、 を使用します <https://security.microsoft.com/tenantAllowBlockList?viewid=SpoofItem> 。 スプーフィング インテリジェンスインサイト **ページに直接移動するには** 、 を使用します <https://security.microsoft.com/spoofintelligence> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - スプーフィング インテリジェンス ポリシーを変更したり、スプーフィング インテリジェンスを有効または無効にするには、組織の管理またはセキュリティ管理者の役割グループのメンバー **である** 必要があります。
  - スプーフィング インテリジェンス ポリシーへの読み取り専用アクセスでは、グローバルリーダーまたはセキュリティ リーダーの役割グループのメンバー **である** 必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  > [!NOTE]
  >
  > - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- EOP および Microsoft Defender のフィッシング対策ポリシーでスプーフィング インテリジェンスを有効または無効にOffice 365。 スプーフィング インテリジェンスは既定で有効になっています。 詳細については[、「EOP で](configure-anti-phishing-policies-eop.md)フィッシング対策ポリシーを構成する」または「Microsoft Defender for Office 365 でフィッシング対策ポリシー[を構成する」を参照してください](configure-mdo-anti-phishing-policies.md)。

- スプーフィング インテリジェンスの推奨設定については [、「EOP フィッシング対策ポリシー設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md#eop-anti-phishing-policy-settings)。

## <a name="open-the-spoof-intelligence-insight-in-the-microsoft-365-defender-portal"></a>スプーフィング インテリジェンスの分析情報を Microsoft 365 Defenderする

1. [ルール] Microsoft 365 Defenderで、[ルール]セクション&[&ルールの脅威ポリシーテナントの許可/ブロックリストをメールで送信する] \>  \>  \> **に移動** します。

2. [テナントの **許可/ブロックリスト] ページ** で、スプーフィング インテリジェンスの分析情報は次のように表示されます。

   ![[フィッシング対策ポリシー] ページのスプーフィング インテリジェンスの分析情報](../../media/m365-sc-spoof-intelligence-insight.png)

   分析情報には、次の 2 つのモードがあります。

   - **インサイト モード**: スプーフィング インテリジェンスが有効になっている場合、過去 7 日間にスプーフィング インテリジェンスによって検出されたメッセージの数が表示されます。
   - **If モード**: スプーフィング インテリジェンスが無効になっている場合、この分析情報は、過去 7 日間にスプーフィング インテリジェンスによって検出されたメッセージの数を示します。

スプーフィング インテリジェンスの検出に関する情報を表示するには、[スプーフィング インテリジェンスの分析情報でスプーフィング **アクティビティ** を表示する] をクリックします。

### <a name="view-information-about-spoofed-messages"></a>スプーフィングされたメッセージに関する情報を表示する

> [!NOTE]
> スプーフィング インテリジェンスによって検出されたスプーフィングされた送信者だけがこのページに表示されます。 インサイトで許可またはブロックの評決を上書きすると、スプーフィングされた送信者は、テナント許可/ブロック一覧の [スプーフィング] タブにのみ表示される手動の許可またはブロック エントリになります。

スプーフィン **グ インテリジェンスインサイト** で [スプーフィング アクティビティの表示] をクリックした後に表示されるスプーフィング インテリジェンスインサイト ページには、次の情報が含まれます。

- **スプーフィング** されたユーザー: メール クライアントの [From] ボックスに表示されるスプーフィング **された** ユーザーのドメイン。 From アドレスは、アドレスとも呼 `5322.From` ばれる。
- **送信インフラストラクチャ**: インフラストラクチャとも呼 _ばれる_。 送信インフラストラクチャは、次のいずれかの値になります。
  - 送信元電子メール サーバーの IP アドレスの逆引き DNS 参照 (PTR レコード) で見つかったドメイン。
  - 送信元 IP アドレスに PTR レコードがない場合、送信インフラストラクチャは \<source IP\> /24 として識別されます (たとえば、192.168.100.100/24 など)。
- **メッセージ数**: スプーフィングされたドメインと送信インフラストラクチャの組み合わせから組織への過去 7 日以内のメッセージの数。
- **最後に** 表示される : スプーフィングされたドメインを含む送信インフラストラクチャからメッセージを受信した最後の日付。
- **スプーフィング** の種類 : 次のいずれかの値を指定します。
  - **内部**: スプーフィングされた送信者は、組織 (受け入れドメイン) に属する [ドメイン内にいます](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
  - **外部**: スプーフィングされた送信者が外部ドメイン内にある。
- **Action**: この値は **許可または****ブロックです**。
  - **許可 :** ドメインで明示的な電子メール認証 [が失敗した場合、SPF、DKIM、](how-office-365-uses-spf-to-prevent-spoofing.md)[および](use-dkim-to-validate-outbound-email.md) [DMARC がチェックされます](use-dmarc-to-validate-email.md)。 ただし、ドメインは暗黙的な電子メール認証チェック (複合認証)[に合格しました](email-validation-and-authentication.md#composite-authentication)。 その結果、メッセージに対してスプーフィング対策アクションは実行されません。
  - **ブロック :** スプーフィングされたドメインと送信インフラストラクチャの組み合わせからのメッセージは、スプーフィング インテリジェンスによって不良とマークされます。 スプーフィングされたメッセージに対して実行されるアクションは、既定のフィッシング対策ポリシーまたはカスタムフィッシング対策ポリシーによって制御されます (既定値は [メッセージを迷惑メール フォルダーに移動 **する]** です)。 詳細については[、「Microsoft Defender でフィッシング対策ポリシー](configure-mdo-anti-phishing-policies.md)を構成する」を参照Office 365。

選択した列見出しをクリックすると、結果を並べ替えできます。

結果をフィルター処理するには、次のオプションがあります。

- [フィルター] **ボタンをクリック** します。 表示される **[フィルター** ] フライアウトで、次の方法で結果をフィルター処理できます。
  - **スプーフィングの種類**
  - **Action**
- [検索 **] ボックス** を使用して、スプーフィングされたドメイン値のコンマ区切りリストを入力するか、インフラストラクチャ値を送信して結果をフィルター処理します。

### <a name="view-details-about-spoofed-messages"></a>スプーフィングされたメッセージの詳細を表示する

リストからエントリを選択すると、次の情報と機能を含む詳細フライアウトが表示されます。

- **ス** プーフィングまたはスプーフィングをブロックする **:** これらの値のいずれかを選択して、元のスプーフィング インテリジェンスの評決を上書きし、スプーフィングの許可またはブロック エントリとしてスプーフィング インテリジェンスインサイトからテナント許可/ブロックリストにエントリを移動します。
- なぜこれをキャッチしたのか。
- 何をする必要があります。
- メインスプーフィング インテリジェンス ページの同じ情報のほとんどを含むドメインの概要。
- 送信者に関する WhoIs データ。
- 脅威エクスプローラーを開く[リンクを](threat-explorer.md)クリックして、[Microsoft Defenderでフィッシングを表示する] の下にある送信者に関する詳細を確認 \> Office 365。
- テナントで同じ送信者から見た同様のメッセージ。

### <a name="about-allowed-spoofed-senders"></a>許可されたスプーフィング送信者について

スプーフィング インテリジェンスインサイトの許可されたスプーフィング送信者、またはスプーフィングを許可するに手動で変更したスプーフィング送信者は、スプーフィングされたドメインと送信側インフラストラクチャの組み合わせからのメッセージのみを許可します。 スプーフィングされたドメインからのメールを任意のソースから許可したり、任意のドメインの送信インフラストラクチャからの電子メールを許可したりはしない。

たとえば、次のスプーフィングされた送信者はスプーフィングを許可されます。

- **ドメイン**: gmail.com
- **インフラストラクチャ**: tms.mx.com

スプーフィングが許可されるのは、そのドメイン/送信インフラストラクチャ ペアからのメールのみです。 スプーフィングを試みる gmail.com 送信者は自動的に許可されません。 スプーフィング インテリジェンスによって引き続 tms.mx.com 他のドメインの送信者からのメッセージは、ブロックされる可能性があります。

## <a name="use-the-spoof-intelligence-insight-in-exchange-online-powershell-or-standalone-eop-powershell"></a>PowerShell またはスタンドアロン EOP PowerShell でスプーフィング インテリジェンスExchange Onlineを使用する

PowerShell では **、Get-SpoofIntelligenceInsight** コマンドレットを使用して、スプーフィング インテリジェンスによって検出された許可およびブロックされたスプーフィング送信者を表示します。 スプーフィングされた送信者を手動で許可またはブロックするには **、New-TenantAllowBlockListSpoofItems コマンドレットを使用する必要** があります。 詳細については、「Use PowerShell を使用して、テナント許可/ブロック一覧へのスプーフィングされた送信者エントリ [を管理する」を参照してください](tenant-allow-block-list.md)。

スプーフィング インテリジェンスインサイトで情報を表示するには、次のコマンドを実行します。

```powershell
Get-SpoofIntelligenceInsight
```

構文とパラメーターの詳細については [、「Get-SpoofIntelligenceInsight」を参照してください](/powershell/module/exchange/get-spoofintelligenceinsight)。

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>スプーフィングとフィッシングを管理するその他の方法

スプーフィングとフィッシング保護について詳しく知る。 ドメインをスプーフィングしている送信者を確認し、組織に損害を与えないよう、関連する方法を次に示します。

- スプーフィン **グ メール レポートを確認します**。 このレポートを頻繁に使用して、スプーフィングされた送信者を表示および管理できます。 詳細については、「スプーフィング [検出レポート」を参照してください](view-email-security-reports.md#spoof-detections-report)。

- 送信者ポリシー フレームワーク (SPF) 構成を確認します。 SPF の概要と SPF を迅速に構成する方法については、「[スプーフィングを防止するために Microsoft 365 で SPF を設定する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)」を参照してください。 Office 365 における SPF の使用方法についての詳細や、ハイブリッド展開などの非標準の展開のトラブルシューティングについては、「[How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)」をご確認ください。

- DomainKeys Identified Mail (DKIM) 構成を確認します。 SPF と DMARC に加えて DKIM を使用して、攻撃者が自分のドメインから送信されたようなメッセージを送信するのを防ぐ必要があります。 DKIM では、電子メール メッセージのメッセージ ヘッダー内にデジタル署名を追加することができます。 詳細については[、「DKIM を使用して、](use-dkim-to-validate-outbound-email.md)カスタム ドメインから送信された送信メールを検証する」を参照Office 365。

- ドメイン ベースのメッセージ認証、レポート、および準拠 (DMARC) 構成を確認します。 SPF および DKIM と共に DMARC を実装すると、メールのスプーフィングやフィッシングに対抗する追加の保護が得られます。 DMARC は、電子メールを受信するシステムが、ドメインから送信された SPF チェックまたは DKIM チェックに失敗したメッセージに対して、どのように対応するかを判断する際に役に立ちます。 詳細については[、「DMARC を使用してメールを検証する」を参照Office 365。](use-dmarc-to-validate-email.md)
