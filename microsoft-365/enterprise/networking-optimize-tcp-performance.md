---
title: '手順 5: クライアントと Office 365 サービスのパフォーマンスを最適化する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: パフォーマンス向上のために TCP 設定と Office 365 サービスを構成します。
ms.openlocfilehash: f89ae816780101c31971c8e3e60df803f82f1e55
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370074"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a>手順 5: クライアントと Office 365 サービスのパフォーマンスを最適化する

*この手順は省略可能で、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます*

![フェーズ 1 - ネットワーキング](./media/deploy-foundation-infrastructure/networking_icon-small.png)

クライアント デバイスと Office 365 の間での伝送制御プロトコル (TCP) の動作を細かく調整することで、パフォーマンスを向上させることができます。

クライアント デバイスでは、TCP パフォーマンスを最適化するため次の TCP 設定を変更できます。

- [TCP ウィンドウ スケーリング](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/): 受信確認が必要となるまでに、クライアント デバイスがより多くのデータを送信できます
- [TCP アイドル時間](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/): クライアント デバイスがオープン接続をより効率的に処理できます
- [TCP 最大セグメント サイズ](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/): クライアント デバイスが 1 つのパケットで最大データ ブロックを送信できます
- [TCP 選択的確認応答](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/): クライアント デバイスが、受信データの確認応答をより効率的に実行できます

Office 365 サービスの場合は、パフォーマンスの最適化については次のリソースを参照してください。

- [Exchange Online](https://docs.microsoft.com/office365/enterprise/tune-exchange-online-performance)
- [Skype for Business Online](https://docs.microsoft.com/office365/enterprise/tune-skype-for-business-online-performance)
- [SharePoint Online](https://docs.microsoft.com/office365/enterprise/tune-sharepoint-online-performance)
- [Project Online の Project Web App](https://docs.microsoft.com/ProjectOnline/tune-project-online-performance)

中間チェックポイントとして、この手順の[終了条件](networking-exit-criteria.md#crit-networking-step5)を確認できます。

## <a name="next-step"></a>次の手順

[ネットワーク インフラストラクチャの終了条件](networking-exit-criteria.md)
