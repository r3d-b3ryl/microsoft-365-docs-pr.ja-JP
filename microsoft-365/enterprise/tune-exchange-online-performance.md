---
title: Exchange Online のパフォーマンスをチューニングする
ms.author: krowley
author: tracyp
manager: laurawi
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: この記事には、パフォーマンスを向上させる方法を示す一般的なヒントと他のリソースへのリンクExchange Online。
ms.openlocfilehash: 0f1a55648b90cfc07a81928f3e30196f9d928bd5271073828500e58138a4007c
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53794656"
---
# <a name="tune-exchange-online-performance"></a>Exchange Online のパフォーマンスをチューニングする

この記事には、移行の前に特に、Exchange Onlineのパフォーマンスを向上させる方法を示す一般的なヒントと他のリソースへのリンクが含まれている。 この記事は、プロジェクトのネットワーク[計画とパフォーマンスの調整Office 365](./network-planning-and-performance.md)です。
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a>パフォーマンスを向上させるために考慮Exchange Online点

移行の速度を向上し、組織の帯域幅の制約を軽減するには、次Exchange Online検討してください。
  
- **メールボックスのサイズを小さくする。** メールボックスのサイズを小さくすると、移行速度が向上します。 
    
- **ハイブリッド展開でメールボックスの移動機能Exchange使用します。** ハイブリッド展開Exchangeオフライン メール (.OST ファイル) に移行するときに再ダウンロードは必要Exchange Online。 これにより、ダウンロード帯域幅の要件が大幅に削減されます。 
    
- **インターネット トラフィックが低く、オンプレミスでの使用が少ない期間中にメールボックスの移動をExchangeします。** 移動をスケジュールする場合、移行要求はメールボックス レプリケーション プロキシに送信され、すぐには実行されない場合があります。 
    
- **ユーザーにリーン ポップアウトをOutlook on the web。** リーン ポップアウトは、Microsoft Edge または Internet Explorer で一部のコンポーネントをレンダリングすることにより、Microsoft Edge または Internet Explorer の特定の電子メール メッセージのメモリ負荷の小さいバージョンを提供します。 詳細については、「無駄のないポップアウトを使用して、メール メッセージを読み取る際に [使用されるメモリを減らす」を参照してください](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)。


## <a name="general-advice"></a>一般的なアドバイス

- ユーザーの DNS 参照が、outlook.office.com の論理的なエントリの場所に MS データセンターを入力します。

- メールボックスキャッシュを調査し、適切なオプションを選択します (再. キャッシュ期間、共有メールボックス キャッシュ、et cetera)。

- インターネットをOutlookする前に、VPN 接続を (中央オフィスに) 転送するデータを保持します。

- メールボックス データがフォルダー、およびアイテムの量に関する制限に準拠している必要があります。
    
移行パフォーマンスの詳細については、「Exchangeパフォーマンスとベスト プラクティスOffice 365[を参照してください](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)。
