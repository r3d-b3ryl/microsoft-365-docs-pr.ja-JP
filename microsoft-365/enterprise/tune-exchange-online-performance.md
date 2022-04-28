---
title: Exchange Online のパフォーマンスをチューニングする
ms.author: krowley
author: tracyp
manager: scotv
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: この記事には、Exchange Onlineのパフォーマンスを向上させる方法を説明する一般的なヒントと他のリソースへのリンクが含まれています。
ms.openlocfilehash: 3b048db5e3ea5090ce5ed2391269f8167c459538
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65092031"
---
# <a name="tune-exchange-online-performance"></a>Exchange Online のパフォーマンスをチューニングする

この記事には、特に移行の前に、Exchange Onlineのパフォーマンスを向上させる方法を説明するその他のリソースへの一般的なヒントとリンクが含まれています。 この記事は、Office 365 プロジェクトの[ネットワーク計画とパフォーマンスのチューニングの](./network-planning-and-performance.md)一部です。
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a>Exchange Onlineのパフォーマンスを向上させるために考慮すべき点

移行の速度を向上させ、Exchange Onlineに対する組織の帯域幅制約を減らすには、次の点を考慮してください。
  
- **メールボックスのサイズを小さくします。** メールボックス サイズを小さくすると、移行速度が向上します。 
    
- **Exchangeハイブリッド展開でメールボックスの移動機能を使用します。** Exchangeハイブリッド展開では、オフライン メール (.OST ファイル) は、Exchange Onlineに移行するときに再ダウンロードする必要はありません。 これにより、ダウンロード帯域幅の要件が大幅に削減されます。 
    
- **インターネット トラフィックが少ない、オンプレミスExchange使用が少ない期間にメールボックスの移動をスケジュールします。** 移動のスケジュールを設定すると、移行要求がメールボックス レプリケーション プロキシに送信され、すぐには実行されない場合があります。 
    
- **Outlook on the webにはリーン ポップアウトを使用します。** リーン ポップアウトは、サーバー上のいくつかのコンポーネントをレンダリングすることで、Microsoft Edgeまたは Internet Explorer の特定の電子メール メッセージのより小さく、メモリ消費の少ないバージョンを提供します。 詳細については、「 [リーン ポップアウトを使用して、メール メッセージを読み取るときに使用されるメモリを減らす](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)」を参照してください。


## <a name="general-advice"></a>一般的なアドバイス

- outlook.office.com の DNS 参照が、お使いの場所の論理エントリの場所に MS データセンターに入っていることを確認します。

- メールボックス のキャッシュを調査し、適切なオプション (re. キャッシュ期間、共有メールボックス キャッシュ、et cetera)。

- インターネットを経由する前に、Outlook データが VPN 接続経由 (中央オフィス) に渡されないようにします。

- メールボックス データが、フォルダーとアイテムの量の制限に従っていることを確認します。
    
移行パフォーマンスのExchangeの詳細については、「[Office 365移行のパフォーマンスとベスト プラクティス](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)」を参照してください。
