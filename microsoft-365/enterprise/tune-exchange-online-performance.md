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
description: この記事には、Exchange Online のパフォーマンスを向上させる方法を示す一般的なヒントと他のリソースへのリンクが含まれている。
ms.openlocfilehash: a7d3268f9f3cf1922319b03cf69d3f044272b27f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909444"
---
# <a name="tune-exchange-online-performance"></a>Exchange Online のパフォーマンスをチューニングする

この記事では、特に移行の前に Exchange Online のパフォーマンスを向上させる方法を説明する一般的なヒントと他のリソースへのリンクについて説明します。 この記事は [、365](./network-planning-and-performance.md) プロジェクトのネットワーク計画とパフォーマンスOfficeです。
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a>Exchange Online のパフォーマンスを向上させるために考慮すべき点

移行の速度を向上し、Exchange Online の組織の帯域幅の制約を減らすには、次の点を検討してください。
  
- **メールボックスのサイズを小さくする。** メールボックスのサイズを小さくすると、移行速度が向上します。 
    
- **Exchange ハイブリッド展開でメールボックス移動機能を使用します。** Exchange ハイブリッド展開では、オフライン メール (.OST ファイル) は、Exchange Online に移行するときに再ダウンロードを必要とします。 これにより、ダウンロード帯域幅の要件が大幅に削減されます。 
    
- **インターネット トラフィックが低く、オンプレミスの Exchange の使用が少ない期間中にメールボックスの移動が発生するスケジュールを設定します。** 移動をスケジュールする場合、移行要求はメールボックス レプリケーション プロキシに送信され、すぐには実行されない場合があります。 
    
- **Outlook on the web でリーン ポップアウトを使用します。** リーン ポップアウトは、サーバー上に一部のコンポーネントをレンダリングすることにより、Microsoft Edge または Internet Explorerの特定の電子メール メッセージのメモリ負荷の小さいバージョンを提供します。 詳細については、「無駄のないポップアウトを使用して、メール メッセージを読み取る際に [使用されるメモリを減らす」を参照してください](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)。


## <a name="general-advice"></a>一般的なアドバイス

- ユーザーの DNS 参照が、outlook.office.com の論理的なエントリの場所に MS データセンターを入力します。

- メールボックスキャッシュを調査し、適切なオプションを選択します (再. キャッシュ期間、共有メールボックス キャッシュ、et cetera)。

- インターネットを通過する前に、Outlook データが VPN 接続を (中央オフィスに) 渡すのをやめておきます。

- メールボックス データがフォルダー、およびアイテムの量に関する制限に準拠している必要があります。
    
Exchange 移行のパフォーマンスの詳細については [、「365 移行Officeベスト プラクティス」を参照してください](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)。
