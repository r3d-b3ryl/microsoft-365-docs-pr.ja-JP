---
title: Microsoft 365 のネットワーク計画とパフォーマンス チューニング
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/19/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_Enterprise
f1.keywords:
- CSH
search.appverid:
- MET150
ms.assetid: e5f1228c-da3c-4654-bf16-d163daee8848
ms.custom:
- seo-marvel-apr2020
- Adm_O365
description: この記事では、Microsoft 365 のネットワーク帯域幅要件を計画し、パフォーマンスの微調整とトラブルシューティングを行う際に役立ちます。
ms.openlocfilehash: bf05e4128f8ba5ddecce76cb00dc945f43c9c59a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923602"
---
# <a name="network-planning-and-performance-tuning-for-microsoft-365"></a>Microsoft 365 のネットワーク計画とパフォーマンス チューニング
初めて展開するか、Microsoft 365 に移行する前に、これらのトピックの情報を使用して必要な帯域幅を見積もり、Microsoft 365 に展開または移行するのに十分な帯域幅をテストして確認できます。 概要については [、「Microsoft 365](network-and-migration-planning.md)のネットワークと移行の計画」を参照してください。
  
|||||
|:-----|:-----|:-----|:-----|
|**ネットワーク計画** <br/> ![ネットワーク](../media/5e9dcd06-601b-4b28-88dc-f524e7548794.png)           <br/> |すばやく読み込む高速な接続とページが必要ですか?  <br/> 「Microsoft [365 で最高の接続性とパフォーマンスを得る」を参照してください](https://aka.ms/o365perfprinciples)。<br/>[概念を理解するには、「Microsoft 365 Network Connectivity Overview」](microsoft-365-networking-overview.md)を参照してください。<br/> |**ネットワークの測定** <br/> ![電卓](../media/d690a132-4884-40eb-a918-526bb3dff3cc.png)           <br/> |ベースライン [とパフォーマンス履歴を使用した Microsoft 365](performance-tuning-using-baselines-and-history.md) のパフォーマンスチューニングと [、Microsoft 365](performance-troubleshooting-plan.md)のパフォーマンスのトラブルシューティング 計画を参照してください。  <br/> 既存のネットワークを評価 [するには、次のツールを使用します](network-and-migration-planning.md#calculators)。  <br/> |
|**ベスト プラクティス** <br/> ![ベスト プラクティス](../media/2a659a5c-1007-47d3-a6c6-a19e018ab29b.png)           <br/> |[Microsoft 365 のネットワーク計画と移行パフォーマンスの](network-and-migration-planning.md#BestPractices)向上に関するベスト プラクティス。 ユーザーを支援する方法を、今すぐ始めてみませんか? 低速 [ネットワークで Office 365 を使用するためのベスト プラクティスを参照してください](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)。  <br/> [Microsoft 365 ネットワーク](./microsoft-365-network-connectivity-principles.md) 接続の原則は、Microsoft 365 ネットワーク接続を安全に最適化するための最新のガイダンスを理解するのに役立ちます。  <br/> |**Reference** <br/> ![書籍またはジャーナル](../media/56dff3c1-f605-48d8-811f-7d13ce639ecd.png)           <br/> |IP アドレスとポートのリストなど、詳細が必要ですか? Microsoft [365 のネットワーク計画リファレンスを参照してください](network-and-migration-planning.md#NetReference)。  <br/> |
|![「Microsoft Cloud Networking for Enterprise Architects」ポスターを参照してください。](../media/3094be9f-2407-4fa5-896d-aa66ef7b9bb9.png)           <br/> |Microsoft 365 および他の Microsoft クラウド プラットフォームとサービスのネットワークを最適化する手順については [、「Microsoft Cloud Networking for Enterprise Architects」](../solutions/cloud-architecture-models.md) ポスターを参照してください。  <br/> |
   
## <a name="performance-tuning-and-troubleshooting-resources-for-microsoft-365"></a>Microsoft 365 のパフォーマンス調整とトラブルシューティングのリソース
<a name="apptuning"> </a>

Microsoft 365 を展開したら、このセクションのトピックを使用してパフォーマンスを最適化できます。 パフォーマンスの低下が発生した場合は、これらのトピックを使用して問題のトラブルシューティングを行います。
  
 **[365 Officeパフォーマンス](tune-microsoft-365-performance.md)** の調整 : Office 365 でのネットワーク アドレス変換の使用の詳細については、「Office [365](nat-support-with-microsoft-365.md)での NAT サポート」を参照してください。 また、365 ネットワーク接続の最適化とトラブルシューティングに関するトップ [10 Officeをご覧ください](/archive/blogs/onthewire/top-10-tips-for-optimising-troubleshooting-your-office-365-network-connectivity)。 
  
 **[Exchange Online のパフォーマンスを調整](tune-exchange-online-performance.md)** する: Exchange Online のパフォーマンスを微調整するには、次の記事を使用します。 
  
 **[Skype for Business Online のパフォーマンスを調整](tune-skype-for-business-online-performance.md)** する: 次の記事を使用して、Skype for Business Online のパフォーマンスを微調整します。 
  
 **[SharePoint Online のパフォーマンスを調整する](tune-sharepoint-online-performance.md)**: SharePoint Online のパフォーマンスを微調整するには、次の記事を使用します。 
  
 **[Project Online のパフォーマンスを調整](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c)** する: この記事を使用して、Project Online のパフォーマンスを微調整します。