---
title: スプーフィング インテリジェンス分析のチュートリアル
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: 管理者は、スプーフィング インテリジェンスの分析情報がどのように機能するのかについて説明します。 電子メール認証チェック (SPF、DKIM、DMARC) に合格しないドメインから組織に電子メールを正当に送信している送信者をすばやく特定できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8ca40e2cde08e5ea213d4c19366f038f1da19fa7
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407218"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>ウォークスルー - Microsoft Defender for microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Defender for Office 365 の Microsoft 365 組織では、スプーフィング インテリジェンスインサイトを使用して、認証されていないメール (SPF、DKIM、または DMARC チェックに合格しないドメインからのメッセージ) を正当に送信している外部送信者をすばやく特定できます。

既知の外部送信者が既知の場所からスプーフィングされたメッセージを送信できるようにすることで、誤検知を減らします (良いメールは悪いとマークされています)。 許可されたスプーフィングされた送信者を監視することで、セキュリティの層を追加して、安全でないメッセージが組織に到着することを防止します。

レポートと分析情報の詳細については、「Security & コンプライアンス センター」 [を参照してください](reports-and-insights-in-security-and-compliance.md)。

このチュートリアルは、コンプライアンス センターのセキュリティ &の 1 つです。 レポートと分析情報のナビゲーションについては、「関連トピック」セクションのチュートリアル [を参照](#related-topics) してください。

> [!NOTE]
> スプーフィング インテリジェンスの分析情報には、過去 7 日間のデータが表示されます。 Exchange Online PowerShell [の](learn-about-spoof-intelligence.md) スプーフィング インテリジェンス ポリシーと対応する [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy) コマンドレットには、過去 30 日間のデータが表示されます。 [Get-SpoofMailReport には](https://docs.microsoft.com/powershell/module/exchange/get-spoofmailreport)、最大 90 日間のデータが表示されます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [セキュリティ ダッシュボード] ページに **直接移動するには** 、 を使用します <https://protection.office.com/searchandinvestigation/dashboard> 。

  スプーフィング インテリジェンスの分析情報は、セキュリティ コンプライアンス センターの複数のダッシュボード&できます。 どのダッシュボードを見ているかにかかわらず、インサイトは同じ詳細を提供し、同じタスクをすばやく実行できます。

- この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります:
  - **組織の管理**
  - **セキュリティ管理者**
  - **セキュリティ閲覧者**
  - **グローバル閲覧者**

  詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

  **注**: Microsoft 365 管理センターの対応する Azure Active Directory ロールにユーザーを追加すると、セキュリティ & コンプライアンスセンターで必要なアクセス許可と、Microsoft 365 の他の機能に対するアクセス許可がユーザーに付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。

- 365 の Microsoft Defender のフィッシング対策ポリシーでスプーフィング インテリジェンスを有効Officeします。 スプーフィング インテリジェンスは既定で有効になっています。 詳細については、「Configure anti-フィッシング ポリシー in [Microsoft Defender for Office 365」を参照してください](configure-atp-anti-phishing-policies.md)。

- スプーフィング インテリジェンスを使用して、認証されていないメッセージを送信している送信者を監視および管理するには、「Configure スプーフィング インテリジェンス in [Microsoft 365」を参照してください](learn-about-spoof-intelligence.md)。

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>セキュリティ コンプライアンス センターでスプーフィング インテリジェンス&開く

1. [セキュリティ とコンプライアンス &] で、[脅威管理ダッシュボード **] に移動** \> **します。**

2. **[Insights] 行** で、次のいずれかの項目を探します。

   - **過去 7 日間に** スプーフィングされたドメインの可能性が高い : この分析情報は、スプーフィング インテリジェンスが有効になっている (既定で有効になっている) かどうかを示します。
   - **スプーフィング保護** を有効にする: この分析情報は、スプーフィング インテリジェンスが無効になっていると示し、その分析情報をクリックするとスプーフィング インテリジェンスを有効にすることができます。

3. ダッシュボードの分析情報には、次のような情報が表示されます。

   ![スプーフィング インテリジェンスの分析情報のスクリーンショット](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   この分析情報には、次の 2 つのモードがあります。

   - **インサイト モード**: スプーフィング インテリジェンスが有効になっている場合、過去 7 日間にスプーフィング インテリジェンス機能によって影響を受けるメッセージの数がインサイトに表示されます。
   - **If モード**: スプーフィング インテリジェンスが無効になっている場合、この分析情報は、過去 7 日間にスプーフィング インテリジェンス機能によって影響を受けるメッセージの数を示します。

   いずれの場合も、インサイトに表示されるスプーフィングされたドメインは、疑わしいドメインと疑わしいドメイン以外の 2 つのカテゴリ **に分けられます**。

   - **疑わしいドメインには、次のものが** 含まれます。

     - 高信頼スプーフィング: ドメインの過去の送信パターンと評判スコアに基づいて、ドメインがスプーフィングを行い、これらのドメインからのメッセージが悪意のある可能性が高いという確信が高いです。

     - 中程度の信頼スプーフィング: 過去の送信パターンとドメインの評判スコアに基づいて、ドメインがスプーフィングを行い、これらのドメインから送信されるメッセージが正当であると適度に確信しています。 誤検知は、高信頼スプーフィングよりもこのカテゴリに含まれる可能性が高いです。

   **疑わしいドメイン以外**: ドメインで明示的な電子メール認証が [失敗し、SPF、DKIM、](how-office-365-uses-spf-to-prevent-spoofing.md)および DMARC が [チェックされます](use-dmarc-to-validate-email.md)。 [](use-dkim-to-validate-outbound-email.md) ただし、ドメインは暗黙的な電子メール認証チェック (複合認証)[に合格しました](email-validation-and-authentication.md#composite-authentication)。 その結果、メッセージに対してスプーフィング対策アクションは実行されません。

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a>スプーフィング インテリジェンスの分析情報から疑わしいドメインに関する詳細情報を表示する

1. スプーフィング インテリジェンスの分析情報で、[疑 **わしい** ドメイン] または [不審でないドメイン] をクリックして、[スプーフィング インテリジェンスの分析情報]**ページに移動** します。 ス **プーフィング インテリジェンスの分析** 情報ページには、次の情報が含まれます。

   - **スプーフィング** されたドメイン: メール クライアントの [From] ボックスに表示されるスプーフィング **された** ユーザーのドメイン。 このアドレスは、アドレスとも呼 `5322.From` ばれる。
   - **インフラストラクチャ**: 送信インフラストラクチャ _とも呼ばれる_。 送信元電子メール サーバーの IP アドレスの逆引き DNS 参照 (PTR レコード) で見つかったドメイン。 送信元 IP アドレスに PTR レコードがない場合、送信インフラストラクチャは \<source IP\> /24 として識別されます (たとえば、192.168.100.100/24 など)。
   - **メッセージ数**: 過去 7 日以内に、指定されたスプーフィングされたドメインを含む送信インフラストラクチャから組織へのメッセージの数。
   - **最後に** 表示される : スプーフィングされたドメインを含む送信インフラストラクチャからメッセージを受信した最後の日付。
   - **スプーフィングの** 種類 : この値は **外部です**。
   - **スプーフィングを許可しますか。**: ここに表示される値は次のとおりです。
     - **は** い : スプーフィングされたユーザーのドメインと送信インフラストラクチャの組み合わせからのメッセージは許可され、スプーフィングされた電子メールとして扱われるのではありません。
     - **いいえ**: スプーフィングされたユーザーのドメインと送信インフラストラクチャの組み合わせからのメッセージは、スプーフィングとしてマークされます。 アクションは、既定のフィッシング対策ポリシーまたはカスタムのフィッシング対策ポリシーによって制御されます (既定値は [メッセージを迷惑メール フォルダーに移動する] **です**)。

     詳細については、「Configure anti-フィッシング ポリシー in [Microsoft Defender for Office 365」を参照してください](configure-atp-anti-phishing-policies.md)。

2. リスト内のアイテムを選択して、フライアウトのドメイン/送信インフラストラクチャ ペアに関する詳細を表示します。 この情報には、次の情報が含まれます。
   - なぜこれをキャッチしたのか。
   - 何をする必要があります。
   - ドメインの概要。
   - 送信者に関する WhoIs データ。
   - テナントで同じ送信者から見た同様のメッセージ。

   ここから、[送信者のスプーフィングを許可する] 一覧からドメイン/送信インフラストラクチャのペアを追加または削除できます。 単にトグルを設定します。

   ![スプーフィング インテリジェンスインサイト詳細ウィンドウのドメインのスクリーンショット](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a>[スプーフィングを許可する] リストへのドメインの追加

スプーフィング インテリジェンスインサイトからスプーフィングを許可するリストにドメインを追加すると、スプーフィングされたドメインと送信インフラストラクチャの組み合わせだけが許可されます。 スプーフィングされたドメインからのメールを任意のソースから許可したり、任意のドメインの送信インフラストラクチャからの電子メールを許可したりはしない。

たとえば、次のドメインを [スプーフィングを許可する] リストに許可します。

- **ドメイン**: gmail.com
- **インフラストラクチャ**: tms.mx.com

スプーフィングが許可されるのは、そのドメイン/送信インフラストラクチャ ペアからのメールのみです。 スプーフィングを試みるgmail.com送信者は許可されません。 スプーフィング インテリジェンスによって、tms.mx.comドメイン内のメッセージがチェックされます。

## <a name="related-topics"></a>関連項目

[Microsoft 365 でのスプーフィング防止保護](anti-spoofing-protection.md)
