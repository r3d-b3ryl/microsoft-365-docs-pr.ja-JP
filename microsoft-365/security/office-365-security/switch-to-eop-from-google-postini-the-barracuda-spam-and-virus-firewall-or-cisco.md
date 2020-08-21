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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
ms.custom:
- seo-marvel-apr2020
description: この記事では、社内の電子メール ハイジェンス アプライアンスまたはクラウドベースの保護サービスから Exchange Online Protection (EOP) に切り替える方法について説明します。
ms.openlocfilehash: a6405411a130abf8369b312f553060caf0bf3855
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827799"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Google Postini、Barracuda Spam、Virus Firewall、Cisco IronPort から EOP に切り替える

 このトピックの目的は、社内の電子メール検疫アプライアンスまたはクラウドベースの保護サービスから Exchange Online Protection (EOP) に切り替えるプロセスを理解していただくことと、着手に役立つリソースを提供することにあります。多数のスパム対策フィルター ソリューションがありますが、多くの場合 EOP への切り替えプロセスは同様です。

EOP を使用するのが新しいお客様が切り替えを決定する前に機能の概要を確認したい場合は [、Exchange Online Protection の概要に関するトピックを読み始](exchange-online-protection-overview.md) めください。

EOP に切り替える前に、Exchange Online、社内、またはハイブリッド シナリオによってクラウド内で EOP 保護されたメールボックスをホストするかどうかを検討することが重要です (ハイブリッドとは、社内でいくつかのメールボックスをホストし、Exchange Online で別の部分をホストすることを意味します)。候補となるこれらの各ホスト シナリオ:クラウド、社内、およびハイブリッドは、セットアップの手順が異なる場合があります。適切な展開を選択するための、いくつかの考慮事項を次に示します。

- **社内メールボックスを使用した EOP 保護**: このシナリオは、使用したい既存のメール ホスティング インフラストラクチャがあるか、社内のメールボックスを保持しなけなけらなけたビジネス要件がある場合、クラウドベースの電子メール保護として EOP を使用したい場合に適しています。 「 [EOP スタンドアロンに切り替える](#switch-to-eop-standalone)」で、このシナリオの詳細を説明しています。

- **Exchange Online メールボックスを使用した EOP 保護**: このシナリオは、EOP 保護とすべてのメールボックスをクラウドでホストしたい場合に適しています。 社内メッセージング サーバーを維持する必要がないため、複雑さを軽減できます。 このシナリオについては、「 [Exchange Online に切り替える](#switch-to-exchange-online)」で説明しています。

- **ハイブリッド メールボックスを使用した EOP 保護**: クラウド メールボックスをお持たしいのですが、一部のユーザーのメールボックスは社内で保持する必要があります。 いくつかのメールボックスを社内でホストし、別の部分を Exchange Online でホストする場合は、このシナリオを選択してください。 このシナリオについては、「 [ハイブリッド ソリューションに切り替える](#switch-to-a-hybrid-solution)」で説明しています。

## <a name="switch-to-eop-standalone"></a>EOP スタンドアロンに切り替える

現在、メールボックスを社内でホストし、社内保護アプライアンスまたはクラウド メッセージング保護サービスを使用している場合は、EOP に切り替えて、その保護機能と可用性を活かすことができます。スタンドアロン シナリオ、つまり、社内でメールボックスをホストし EOP を使用して電子メール保護を提供するように EOP を設定するには、「[EOP サービスを設定する](set-up-your-eop-service.md)」で概説されている手順に従います。このトピックでは、サインアップ、ドメインの追加、コネクタとのメール フローの設定などの、EOP 保護の設定に関する手順を概説しています。

## <a name="switch-to-exchange-online"></a>Exchange Online に切り替える

オンプレミスのメールボックスをオンプレミスのアプライアンスによって保護してきらい、Microsoft 365 のクラウドのメッセージングおよび保護機能を活用して Exchange Online クラウド ホスト型メールボックスおよび EOP 保護に移行したいとおり。 作業を開始するには、Microsoft 365 にサインアップして、ドメインを追加します。 このシナリオでは、オンプレミス メールボックスにいかならないため、コネクタを設定する必要がなければいけません。 まず、 [サインアップしてその機能を使い慣れている Microsoft 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) の最新の高度な機能を利用できます。

Microsoft 365 の設定プロセスでは、クラウドベースのメールボックス ユーザーを作成します。

## <a name="switch-to-a-hybrid-solution"></a>ハイブリッド ソリューションに切り替える

ビジネス要件または規制に関する考慮事項があるため、メールボックスの一部のみをクラウドに移行したい場合があります。このようなケースでは、ハイブリッド シナリオを展開すると、ビジネス要件に従ってメールボックスをクラウドに移行できます。EOP 保護を使用したハイブリッド シナリオへの移行は、すべてにおいてクラウドを採用するシナリオより複雑ですが、Microsoft には、ハイブリッドへの移行が簡単に行える数多くのハイブリッド サポートとリソースが用意されています。

ハイブリッド展開を検討している場合は、ハイブリッド展開をExchange Server [最適です](https://docs.microsoft.com/exchange/exchange-hybrid)。 さらに、ハイブリッド シナリオではメールをルーティングできるいくつかの異なる方法があり、それらを理解しておくことが重要です。 [Exchange ハイブリッド展開でのトランスポート ルーティングは、](https://docs.microsoft.com/exchange/transport-routing) それぞれのタイプについて説明するので、ビジネス要件に基づいて最適なルーティング シナリオを選択することができます。

## <a name="migration-planning"></a>移行の計画

EOP への切り替えを決定したら、特に次の分野について考慮する必要があります。

- **カスタム フィルター処理ルール**: 特定のスパムを検出するためのカスタム フィルター処理またはビジネス ポリシー ルールがある場合は、一定期間、一定期間、ルールを移行する前に既定の設定で EOP を試してみてください。 EOP は既定の設定でエンタープライズ レベルのスパム対策を提供しているため、一部のルールを EOP に移行する必要がない場合があります。 当然、特定のカスタム ビジネス ポリシーを適用するルールがある場合には、それらを作成できます。 [Exchange Online Protection のメール フロー ルール (トランスポート ルール) では、EOP](mail-flow-rules-transport-rules-0.md) でメール フロー ルールを作成する詳細な手順が提供されます。

- **IP 許可一覧と IP 禁止一**覧: ユーザーごとの許可リストと禁止一覧がある場合は、設定プロセスの一部としてその一覧を EOP にコピーできます。 IP 許可一覧と IP 禁止一覧の詳細については、「接続フィルター [ポリシーを構成する」を参照してください](configure-the-connection-filter-policy.md)。

- **セキュ**ア通信: 暗号化メッセージングが必要なパートナーがいない場合は、これを Exchange 管理センターで設定するようにしてください。 このシナリオを構成するには、「 [パートナー組織とのセキュリティで保護されたメール フロー用のコネクタを設定する」を参照してください](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)。

> [!TIP]
> 社内アプライアンスから EOP に切り替える場合は、ビジネス ルールのチェックを実行するアプライアンスまたはサーバーを配置したままにしておくことができます。 たとえば、アプライアンスが送信メールのカスタム フィルター処理を実行し、それを継続して実行したい場合は、メールをインターネットにルーティングする前に、直接アプライアンスに送信して追加のフィルター処理を行うように EOP を構成できます。
