---
title: Office 365 サービスに接続するネットワーク デバイスの計画
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/29/2016
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 073433ca-3511-4db9-b173-7a2edca57691
description: '概要: Office 365への接続に使用されるネットワーク容量、WAN アクセラレータ、および負荷分散デバイスに関する考慮事項について説明します。'
ms.openlocfilehash: 58c4225d9d381dabedfa86d81ced7f5922932058
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65100327"
---
# <a name="plan-for-network-devices-that-connect-to-office-365-services"></a>Office 365 サービスに接続するネットワーク デバイスの計画

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*
  
一部のネットワーク ハードウェアでは、サポートされている同時セッションの数に制限がある場合があります。 ユーザーが 2,000 人を超える組織の場合は、ネットワーク デバイスを監視して、追加のOffice 365 サービス トラフィックを処理できることを確認することをお勧めします。 簡易ネットワーク管理プロトコル (SNMP) 監視ソフトウェアは、これを行うのに役立ちます。

この記事は、[Office 365のネットワーク計画とパフォーマンスのチューニングの](./network-planning-and-performance.md)一部です。

オンプレミスの発信インターネット プロキシ設定は、クライアント アプリケーションのOffice 365 サービスへの接続にも影響します。 また、Microsoft クラウド サービスの URL とアプリケーションの接続を許可するようにネットワーク プロキシ デバイスを構成する必要もあります。 すべての組織が異なります。 Microsoft がこのプロセスを管理する方法と、プロビジョニングする帯域幅の量を把握するには、 [ケース スタディを参照](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)してください。
  
Skype for Business設定の詳細については、次のSkype for Businessヘルプ記事を参照してください。
  
- [管理者向けのオンライン サインイン エラー Skype for Businessトラブルシューティング](/skypeforbusiness/set-up-skype-for-business-online/troubleshooting-sign-in-errors-for-admins)

- [オンプレミスファイアウォールによって接続がブロックされるため、Skype for Businessに接続できない、または特定の機能が機能しない](https://go.microsoft.com/fwlink/p/?LinkID=243625)

> [!NOTE]
> これらの設定の多くはSkype for Business固有ですが、ネットワーク構成に関する一般的なガイダンスは、すべてのOffice 365 サービスに役立ちます。
  
## <a name="determining-network-capacity"></a>ネットワーク容量の決定

接続に存在するすべてのネットワーク デバイスには、その容量制限があります。 これらのデバイスには、クライアントとサーバーのネットワーク アダプター、ルーター、スイッチ、およびそれらを相互接続するハブが含まれます。 適切なネットワーク容量は、飽和状態のネットワーク容量が存在しないという意味です。 ネットワーク アクティビティを監視することは、すべてのネットワーク デバイスの実際の負荷が最大容量を下回っていることを確認するために不可欠です。 ネットワーク容量は、プロキシ デバイスのパフォーマンスに影響します。
  
ほとんどの場合、インターネット接続帯域幅はトラフィック量の制限を設定します。 ピーク 時のパフォーマンスの低下は、インターネット リンクの過度な使用が原因と考えられます。 この状況は、ブランチ オフィス プロキシ サーバー コンピューターが低速のワイド エリア ネットワーク (WAN) リンク経由でブランチの本社のプロキシ デバイスに接続されているブランチ オフィスのシナリオにも適用されます。
  
ネットワーク容量をテストするには、プロキシ ネットワーク インターフェイスでネットワーク アクティビティを監視します。 ネットワーク インターフェイスの最大帯域幅の 75% を超える場合は、不十分なネットワーク インフラストラクチャの帯域幅を増やすことを検討してください。 または、HTTP 圧縮などの高度な機能の使用を検討してください。
  
## <a name="wan-accelerators"></a>WAN アクセラレータ

組織でワイド エリア ネットワーク (WAN) アクセラレーション プロキシ アプライアンスを使用している場合は、Office 365 サービスにアクセスするときに問題が発生する可能性があります。 ネットワーク デバイスまたはデバイスを最適化して、ユーザーがOffice 365にアクセスするときに一貫したエクスペリエンスを確保する必要がある場合があります。 たとえば、Office 365 サービスは、一部のOffice 365コンテンツと TCP ヘッダーを暗号化します。 デバイスでは、この種のトラフィックを処理できない場合があります。
  
[Office 365での WAN 最適化コントローラーまたは Traffic/Inspection デバイスの使用](https://support.microsoft.com/kb/2690045)に関するサポート ステートメントを参照してください。
  
## <a name="hardware-and-software-load-balancing-devices"></a>ハードウェアおよびソフトウェア負荷分散デバイス

組織では、ハードウェア ロード バランサー (HLB) またはネットワーク負荷分散 (NLB) ソリューションを使用して、Active Directory フェデレーション サービス (AD FS) (AD FS) サーバーやExchangeハイブリッド サーバーに要求を配布する必要があります。 負荷分散デバイスは、オンプレミス サーバーへのネットワーク トラフィックを制御します。 これらのサーバーは、シングル サインオンとExchangeハイブリッド展開の可用性を確保するうえで非常に重要です。
  
Windows Server に組み込まれているソフトウェア ベースの NLB ソリューションを提供します。 Office 365 は、このソリューションをサポートすることによって負荷分散を実現します。
  
## <a name="firewalls-and-proxies"></a>ファイアウォールとプロキシ

Office 365に接続するためのファイアウォールとプロキシの構成の詳細については、「[Office 365 エンドポイントの管理](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)」、「[Office 365ネットワーク接続の評価](assessing-network-connectivity.md)」、「[Office 365 エンドポイントに関する FAQ」](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)を参照して、デバイスと回線の選択の詳細を確認してください。
  
## <a name="see-also"></a>関連項目

[Office 365 サービスのセットアップ ガイド](setup-guides-for-microsoft-365.md)

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)