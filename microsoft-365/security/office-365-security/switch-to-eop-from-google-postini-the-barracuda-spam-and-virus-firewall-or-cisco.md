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
localization_priority: Normal
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
ms.custom:
- seo-marvel-apr2020
description: この記事では、オンプレミスの電子メールの安全対策アプライアンスまたはクラウドベースの保護サービスから Exchange Online Protection (EOP) に切り替える方法について学習します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0cb946fbb60393657aab21195bc4dd723458f16e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290191"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Google Postini、Barracuda Spam、Virus Firewall、Cisco IronPort から EOP に切り替える

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

 このトピックの目的は、社内の電子メール検疫アプライアンスまたはクラウドベースの保護サービスから Exchange Online Protection (EOP) に切り替えるプロセスを理解していただくことと、着手に役立つリソースを提供することにあります。多数のスパム対策フィルター ソリューションがありますが、多くの場合 EOP への切り替えプロセスは同様です。

EOP を使い始めて、切り替える前に機能の概要を確認する場合は、まず [Exchange Online Protection](exchange-online-protection-overview.md) の概要トピックを参照してください。

EOP に切り替える前に、Exchange Online、社内、またはハイブリッド シナリオによってクラウド内で EOP 保護されたメールボックスをホストするかどうかを検討することが重要です (ハイブリッドとは、社内でいくつかのメールボックスをホストし、Exchange Online で別の部分をホストすることを意味します)。候補となるこれらの各ホスト シナリオ:クラウド、社内、およびハイブリッドは、セットアップの手順が異なる場合があります。適切な展開を選択するための、いくつかの考慮事項を次に示します。

- オンプレミスのメールボックスを使用した EOP 保護: このシナリオは、使用する既存のメール ホスティング インフラストラクチャがある場合や、メールボックスをオンプレミスに維持するビジネス要件がある場合、およびクラウドベースの電子メール保護として **EOP** を使用する場合に適しています。 「 [EOP スタンドアロンに切り替える](#switch-to-eop-standalone)」で、このシナリオの詳細を説明しています。

- **Exchange Online メールボックス** を使用した EOP 保護 : このシナリオは、EOP 保護とすべてのメールボックスをクラウドでホストする場合に適しています。 社内メッセージング サーバーを維持する必要がないため、複雑さを軽減できます。 このシナリオについては、「 [Exchange Online に切り替える](#switch-to-exchange-online)」で説明しています。

- **ハイブリッド メールボックスを使用した EOP** 保護 : クラウド メールボックスが必要な場合がありますが、一部のユーザーのメールボックスはオンプレミスに保持する必要があります。 いくつかのメールボックスを社内でホストし、別の部分を Exchange Online でホストする場合は、このシナリオを選択してください。 このシナリオについては、「 [ハイブリッド ソリューションに切り替える](#switch-to-a-hybrid-solution)」で説明しています。

## <a name="switch-to-eop-standalone"></a>EOP スタンドアロンに切り替える

現在、メールボックスを社内でホストし、社内保護アプライアンスまたはクラウド メッセージング保護サービスを使用している場合は、EOP に切り替えて、その保護機能と可用性を活かすことができます。スタンドアロン シナリオ、つまり、社内でメールボックスをホストし EOP を使用して電子メール保護を提供するように EOP を設定するには、「[EOP サービスを設定する](set-up-your-eop-service.md)」で概説されている手順に従います。このトピックでは、サインアップ、ドメインの追加、コネクタとのメール フローの設定などの、EOP 保護の設定に関する手順を概説しています。

## <a name="switch-to-exchange-online"></a>Exchange Online に切り替える

オンプレミスのアプライアンスで保護されたオンプレミスのメールボックスを使用している場合、Exchange Online のクラウド ホスト型メールボックスと EOP 保護に移動して、Microsoft 365 のクラウド メッセージングと保護機能を活用したい場合があります。 開始するには、Microsoft 365 にサインアップしてドメインを追加します。 このシナリオでは、オンプレミスのメールボックスへのルーティングが存在しないので、コネクタを設定する必要はありません。 まず [、Microsoft 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) で最新の高度な機能を取得してサインアップし、その機能を理解します。

Microsoft 365 のセットアップ プロセス中に、クラウドベースのメールボックス ユーザーを作成します。

## <a name="switch-to-a-hybrid-solution"></a>ハイブリッド ソリューションに切り替える

ビジネス要件または規制に関する考慮事項があるため、メールボックスの一部のみをクラウドに移行したい場合があります。このようなケースでは、ハイブリッド シナリオを展開すると、ビジネス要件に従ってメールボックスをクラウドに移行できます。EOP 保護を使用したハイブリッド シナリオへの移行は、すべてにおいてクラウドを採用するシナリオより複雑ですが、Microsoft には、ハイブリッドへの移行が簡単に行える数多くのハイブリッド サポートとリソースが用意されています。

ハイブリッド展開を検討している場合、最初に最も良い場所は、ハイブリッド展開 [Exchange Serverです](https://docs.microsoft.com/exchange/exchange-hybrid)。 さらに、ハイブリッド シナリオではメールをルーティングできるいくつかの異なる方法があり、それらを理解しておくことが重要です。 [Exchange ハイブリッド展開でのトランスポート](https://docs.microsoft.com/exchange/transport-routing) ルーティングでは、それぞれの種類について説明します。そのため、ビジネス要件に基づいて最適なルーティング シナリオを選択できます。

## <a name="migration-planning"></a>移行の計画

EOP への切り替えを決定したら、特に次の分野について考慮する必要があります。

- **カスタム フィルター処理ルール**: 特定のスパムをキャッチするカスタム フィルタールールまたはビジネス ポリシー ルールがある場合は、ルールを移行する前に、一期間、既定の設定で EOP を試しにすることをお勧めします。 EOP は既定の設定でエンタープライズ レベルのスパム対策を提供しているため、一部のルールを EOP に移行する必要がない場合があります。 当然、特定のカスタム ビジネス ポリシーを適用するルールがある場合には、それらを作成できます。 [Exchange Online Protection のメール](mail-flow-rules-transport-rules-0.md) フロー ルール (トランスポート ルール) は、EOP でメール フロー ルールを作成するための詳細な手順を提供します。

- **IP 許可一覧と IP** ブロック 一覧 : ユーザー単位の許可一覧とブロック リストがある場合は、セットアップ プロセスの一環として、一覧を EOP にコピーする時間を取る必要があります。 IP 許可一覧と IP ブロック一覧の詳細については、「接続フィルター ポリシーを構成 [する」を参照してください](configure-the-connection-filter-policy.md)。

- **セキュリティで** 保護された通信 : パートナーが暗号化されたメッセージングを必要とする場合は、Exchange 管理センターで設定することをお勧めします。 このシナリオを構成するには、「 [パートナー組織とのセキュリティで保護されたメール フローのためのコネクタの設定」を参照してください](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)。

> [!TIP]
> 社内アプライアンスから EOP に切り替える場合は、ビジネス ルールのチェックを実行するアプライアンスまたはサーバーを配置したままにしておくことができます。 たとえば、アプライアンスが送信メールに対してカスタム フィルタリングを実行し、それを続行する場合は、インターネットにルーティングされる前に、追加のフィルタリングのために直接アプライアンスにメールを送信する EOP を構成できます。
