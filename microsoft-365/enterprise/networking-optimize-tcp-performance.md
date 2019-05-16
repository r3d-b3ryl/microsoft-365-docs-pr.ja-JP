---
title: '手順 5: クライアントと Office 365 サービスのパフォーマンスを最適化する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: パフォーマンス向上のために TCP 設定と Office 365 サービスを構成します。
ms.openlocfilehash: 9e786b36d7a2afccc3b9112b815cd42a40317c15
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073187"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a>手順 5: クライアントと Office 365 サービスのパフォーマンスを最適化する

*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

クライアント デバイスと Office 365 の間での伝送制御プロトコル (TCP) の動作を細かく調整することで、パフォーマンスを向上させることができます。

クライアント デバイスでは、TCP パフォーマンスを最適化するため次の TCP 設定を変更できます。

- [TCP ウィンドウ スケーリング](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/): 受信確認が必要となるまでに、クライアント デバイスがより多くのデータを送信できます
- [TCP アイドル時間](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/): クライアント デバイスがオープン接続をより効率的に処理できます
- [TCP 最大セグメント サイズ](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/): クライアント デバイスが 1 つのパケットで最大データ ブロックを送信できます
- [TCP 選択的確認応答](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/): クライアント デバイスが、受信データの確認応答をより効率的に実行できます

Office 365 サービスの場合は、パフォーマンスの最適化については次のリソースを参照してください。

- [Exchange Online](https://support.office.com/article/Tune-Exchange-Online-performance-026e83cb-a945-4543-97b0-a8af6e80ac61)
- [Skype for Business Online](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802)
- [SharePoint Online](https://support.office.com/article/Tune-SharePoint-Online-performance-f0522d4a-fbf4-41f9-854e-c9b59555091d)
- [Project Online](https://support.office.com/article/Tune-Project-Online-performance-12ba0ebd-c616-42e5-b9b6-cad570e8409c)

中間チェックポイントとして、この手順の[終了条件](networking-exit-criteria.md#crit-networking-step5)を確認できます。

## <a name="next-step"></a>次の手順

[ネットワーク インフラストラクチャの終了条件](networking-exit-criteria.md)
