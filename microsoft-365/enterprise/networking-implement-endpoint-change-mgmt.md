---
title: '手順 4: URL と IP アドレスの変更を計画する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ''
ms.openlocfilehash: dacd2ad83bdeb106ae398e8223f457c66a12b598
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073227"
---
# <a name="step-4-plan-for-url-and-ip-address-changes"></a>手順 4: URL と IP アドレスの変更を計画する

*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

>[!Note]
>この手順を実行するには[手順 3](networking-configure-proxies-firewalls.md) を実行している必要があります。手順 3 を実行していない場合は、[手順 5](networking-optimize-tcp-performance.md) に進むことができます。
>

Microsoft 365 グローバル ネットワークで使用される URL と IP アドレスは、時間の経過とともに変化します。このため、これらのエンドポイントの更新を計画することが重要です。たとえば、次の情報を使用してセキュリティ境界デバイスを再構成することが必要な場合があります。

- 制限のない処理を必要とする新しいサービスの新しい URL
- 廃止となったサービスの削除済み URL
- インターネット上の新しい Microsoft ネットワークの場所とサーバーの新しい IP アドレス範囲 
- 各種サービスの IP アドレス範囲の変更

エンドポイントの変更の実装計画 (変更の通知を含む) の策定に関する詳細については、「[Office 365 エンドポイントを管理する - 統合](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration)」および「[Office 365 エンドポイントを管理する - プロキシ](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies)」を参照してください。

中間チェックポイントとして、この手順の[終了条件](networking-exit-criteria.md#crit-networking-step4)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[クライアントと Office 365 サービスのパフォーマンスを最適化する](networking-optimize-tcp-performance.md)|
