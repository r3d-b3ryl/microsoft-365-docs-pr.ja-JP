---
title: Office 365 サービスに接続するネットワーク デバイスの計画
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/29/2016
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 073433ca-3511-4db9-b173-7a2edca57691
description: '概要: ネットワーク容量、WAN アクセラレータ、およびデバイスへの接続に使用される負荷分散デバイスに関する考慮事項についてOffice 365。'
ms.openlocfilehash: bda9fc9e9005530e97bc0033fc13813fceeb77d84e39f44726d259fd8847e8e8
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53894901"
---
# <a name="plan-for-network-devices-that-connect-to-office-365-services"></a>Office 365 サービスに接続するネットワーク デバイスの計画

*この記事は、Microsoft 365 Enterprise と Office 365 Enterprise の両方に適用されます。*
  
一部のネットワーク ハードウェアでは、サポートされている同時セッションの数に制限がある場合があります。 2,000 人を超えるユーザーを持つ組織では、ネットワーク デバイスを監視して、追加のサービス トラフィックを処理Office 365することをお勧めします。 簡易ネットワーク管理プロトコル (SNMP) 監視ソフトウェアは、これを行うのに役立ちます。

この記事は、ネットワークの計画と[パフォーマンスの調整](./network-planning-and-performance.md)の一部Office 365。

オンプレミスの送信インターネット プロキシ設定は、クライアント アプリケーションのOffice 365接続にも影響します。 また、Microsoft クラウド サービスの URL とアプリケーションへの接続を許可するネットワーク プロキシ デバイスを構成する必要があります。 すべての組織が異なります。 Microsoft がこのプロセスを管理する方法と、プロビジョニングする帯域幅の量を確認するには、ケース [スタディを参照してください](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)。
  
次のヘルプSkype for Businessの設定に関する詳細Skype for Business示します。
  
- [管理者Skype for Businessオンライン サインイン エラーのトラブルシューティング](/skypeforbusiness/set-up-skype-for-business-online/troubleshooting-sign-in-errors-for-admins)

- [オンプレミスファイアウォールが接続Skype for Business、または特定の機能が機能しない場合は、接続をブロックします。](https://go.microsoft.com/fwlink/p/?LinkID=243625)

> [!NOTE]
> これらの設定の多くはSkype for Business固有ですが、ネットワーク構成に関する一般的なガイダンスは、すべてのサービスOffice 365です。
  
## <a name="determining-network-capacity"></a>ネットワーク容量の決定

接続に存在するネットワーク デバイスには、容量制限があります。 これらのデバイスには、クライアントとサーバーのネットワーク アダプター、ルーター、スイッチ、およびそれらを相互接続するハブが含まれます。 適切なネットワーク容量は、どのネットワーク容量も飽和状態でいなかっているという意味です。 ネットワーク アクティビティの監視は、すべてのネットワーク デバイスの実際の負荷が最大容量より小さい状態を確保するために不可欠です。 ネットワーク容量は、プロキシ デバイスのパフォーマンスに影響します。
  
ほとんどの場合、インターネット接続帯域幅はトラフィック量の制限を設定します。 トラフィックのピーク時のパフォーマンスが低下する原因は、インターネット リンクが過剰に使用されている可能性があります。 この状況は、ブランチ オフィス のプロキシ サーバー コンピューターが低速のワイド エリア ネットワーク (WAN) リンクを使用してブランチの本社のプロキシ デバイスに接続されるブランチ オフィスのシナリオにも適用されます。
  
ネットワーク容量をテストするには、プロキシ ネットワーク インターフェイスでネットワーク アクティビティを監視します。 ネットワーク インターフェイスの最大帯域幅の 75% を超える場合は、不十分なネットワーク インフラストラクチャの帯域幅を増やしてください。 または、HTTP 圧縮などの高度な機能の使用を検討してください。
  
## <a name="wan-accelerators"></a>WAN アクセラレータ

組織でワイド エリア ネットワーク (WAN) アクセラレーション プロキシ アプライアンスを使用している場合は、ネットワーク サービスにアクセスするときに問題Office 365があります。 ネットワーク デバイスまたはデバイスを最適化して、ユーザーがネットワーク デバイスにアクセスするときに一貫性のあるエクスペリエンスをOffice 365。 たとえば、サービスOffice 365コンテンツと TCP ヘッダー Office 365暗号化します。 デバイスでこの種類のトラフィックを処理できない場合があります。
  
WAN 最適化コントローラーまたはトラフィック[/](https://support.microsoft.com/kb/2690045)検査デバイスを使用する方法に関するサポート ステートメントを参照Office 365。
  
## <a name="hardware-and-software-load-balancing-devices"></a>ハードウェアおよびソフトウェア負荷分散デバイス

組織では、ハードウェア ロード バランサー (HLB) またはネットワーク負荷分散 (NLB) ソリューションを使用して、Active Directory フェデレーション サービス (AD FS) サーバーや Exchange ハイブリッド サーバーに要求を配布する必要があります。 負荷分散デバイスは、オンプレミス サーバーへのネットワーク トラフィックを制御します。 これらのサーバーは、シングル サインオンとハイブリッド展開の可用性を確保Exchange重要です。
  
ソフトウェア ベースの NLB ソリューションは、サーバーに組み込Windows提供します。 Office 365 は、このソリューションをサポートすることによって負荷分散を実現します。
  
## <a name="firewalls-and-proxies"></a>ファイアウォールとプロキシ

Office 365 に接続するためのファイアウォールとプロキシの構成の詳細については、「Office 365 エンドポイントの管理」、Office 365 ネットワーク接続の評価、および[](assessing-network-connectivity.md)Office 365 エンドポイントに関する[FAQ](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)を参照して、デバイスと回線の選択の詳細について説明します。 [](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
## <a name="see-also"></a>関連項目

[サービスのセットアップ Office 365ガイド](setup-guides-for-microsoft-365.md)

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)