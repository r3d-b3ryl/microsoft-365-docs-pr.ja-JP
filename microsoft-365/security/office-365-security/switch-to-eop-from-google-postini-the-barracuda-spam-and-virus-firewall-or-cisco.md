---
title: 別の保護サービスから EOP に切り替える
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
ms.custom:
- seo-marvel-apr2020
description: この記事では、オンプレミスの電子メール衛生アプライアンスまたはクラウドベースの保護サービスから Exchange Online Protection (EOP) に切り替える方法について学習します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9b1bd7eb869c410ccbda51ad88b105ff0315fadd
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60149591"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Google Postini、Barracuda Spam、Virus Firewall、Cisco IronPort から EOP に切り替える

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

 このトピックの目的は、社内の電子メール検疫アプライアンスまたはクラウドベースの保護サービスから Exchange Online Protection (EOP) に切り替えるプロセスを理解していただくことと、着手に役立つリソースを提供することにあります。多数のスパム対策フィルター ソリューションがありますが、多くの場合 EOP への切り替えプロセスは同様です。

EOP を使い始めて、切り替える前に機能の概要を読む場合は、「概要」のトピックからExchange Online Protection[してください](exchange-online-protection-overview.md)。

EOP に切り替える前に、Exchange Online、社内、またはハイブリッド シナリオによってクラウド内で EOP 保護されたメールボックスをホストするかどうかを検討することが重要です (ハイブリッドとは、社内でいくつかのメールボックスをホストし、Exchange Online で別の部分をホストすることを意味します)。候補となるこれらの各ホスト シナリオ:クラウド、社内、およびハイブリッドは、セットアップの手順が異なる場合があります。適切な展開を選択するための、いくつかの考慮事項を次に示します。

- オンプレミスメールボックスによる **EOP** 保護: このシナリオは、使用する既存のメール ホスティング インフラストラクチャがある場合、またはメールボックスをオンプレミスに維持するビジネス要件がある場合、およびクラウドベースの電子メール保護として EOP を使用する場合に適しています。 「 [EOP スタンドアロンに切り替える](#switch-to-eop-standalone)」で、このシナリオの詳細を説明しています。

- **EOP 保護と** Exchange Online: このシナリオは、EOP 保護とすべてのメールボックスをクラウドでホストする場合に適しています。 社内メッセージング サーバーを維持する必要がないため、複雑さを軽減できます。 このシナリオについては、「 [Exchange Online に切り替える](#switch-to-exchange-online)」で説明しています。

- **ハイブリッド メールボックスを使用した EOP** 保護 : クラウド メールボックスが必要な場合がありますが、一部のユーザーのメールボックスはオンプレミスに保持する必要があります。 いくつかのメールボックスを社内でホストし、別の部分を Exchange Online でホストする場合は、このシナリオを選択してください。 このシナリオについては、「 [ハイブリッド ソリューションに切り替える](#switch-to-a-hybrid-solution)」で説明しています。

## <a name="switch-to-eop-standalone"></a>EOP スタンドアロンに切り替える

現在、メールボックスを社内でホストし、社内保護アプライアンスまたはクラウド メッセージング保護サービスを使用している場合は、EOP に切り替えて、その保護機能と可用性を活かすことができます。スタンドアロン シナリオ、つまり、社内でメールボックスをホストし EOP を使用して電子メール保護を提供するように EOP を設定するには、「[EOP サービスを設定する](/exchange/standalone-eop/set-up-your-eop-service)」で概説されている手順に従います。このトピックでは、サインアップ、ドメインの追加、コネクタとのメール フローの設定などの、EOP 保護の設定に関する手順を概説しています。

## <a name="switch-to-exchange-online"></a>Exchange Online に切り替える

オンプレミスのアプライアンスで保護されたオンプレミスのメールボックスがある場合、Microsoft 365 クラウド メッセージングと保護機能を利用するために、Exchange Online クラウドホスト型メールボックスと EOP 保護にジャンプする必要があります。 開始するには、ドメインにサインアップしてMicrosoft 365追加します。 このシナリオでは、オンプレミスのメールボックスへのルーティングが存在しないので、コネクタをセットアップする必要はありません。 「最新の[高度な機能](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans)を使ってサインアップMicrosoft 365機能を理解する」から始めましょう。

セットアップ プロセスMicrosoft 365、クラウドベースのメールボックス ユーザーを作成します。

## <a name="switch-to-a-hybrid-solution"></a>ハイブリッド ソリューションに切り替える

ビジネス要件または規制に関する考慮事項があるため、メールボックスの一部のみをクラウドに移行したい場合があります。このようなケースでは、ハイブリッド シナリオを展開すると、ビジネス要件に従ってメールボックスをクラウドに移行できます。EOP 保護を使用したハイブリッド シナリオへの移行は、すべてにおいてクラウドを採用するシナリオより複雑ですが、Microsoft には、ハイブリッドへの移行が簡単に行える数多くのハイブリッド サポートとリソースが用意されています。

ハイブリッド展開を検討する場合は、ハイブリッド展開を開始するExchange Server[です](/exchange/exchange-hybrid)。 さらに、ハイブリッド シナリオではメールをルーティングできるいくつかの異なる方法があり、それらを理解しておくことが重要です。 [ハイブリッド展開Exchangeトランスポート](/exchange/transport-routing)ルーティングでは、各種類について説明します。そのため、ビジネス要件に基づいて最適なルーティング シナリオを選択できます。

## <a name="migration-planning"></a>移行の計画

EOP への切り替えを決定したら、特に次の分野について考慮する必要があります。

- **カスタム フィルター ルール**: 特定のスパムをキャッチするカスタム フィルタールールまたはビジネス ポリシー ルールがある場合は、ルールを移行する前に、一期間既定の設定で EOP を試することをお勧めします。 EOP は既定の設定でエンタープライズ レベルのスパム対策を提供しているため、一部のルールを EOP に移行する必要がない場合があります。 当然、特定のカスタム ビジネス ポリシーを適用するルールがある場合には、それらを作成できます。 詳細については、「[Mail flow rules (transport rules) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)」を参照してください。

- **IP 許可リストと IP** ブロック リスト : ユーザーごとの許可リストとブロック リストがある場合は、セットアップ プロセスの一環としてリストを EOP にコピーする時間を割り当てします。 IP 許可一覧と IP ブロック 一覧の詳細については、「接続フィルター ポリシーの構成 [」を参照してください](configure-the-connection-filter-policy.md)。

- **セキュリティで保護** された通信: 暗号化されたメッセージングが必要なパートナーがある場合は、管理センターでこれをExchange勧めします。 このシナリオを構成するには、「パートナー組織とのセキュリティで保護されたメール フロー用にコネクタを設定 [する」を参照してください](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)。

> [!TIP]
> 社内アプライアンスから EOP に切り替える場合は、ビジネス ルールのチェックを実行するアプライアンスまたはサーバーを配置したままにしておくことができます。 たとえば、アプライアンスが送信メールに対してカスタム フィルター処理を実行し、その処理を続行する場合は、インターネットにルーティングされる前に、追加のフィルター処理のためにアプライアンスに直接メールを送信する EOP を構成できます。
