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
description: この記事では、ネットワーク帯域幅の要件を計画し、パフォーマンスMicrosoft 365調整およびトラブルシューティングを行う際に役立ちます。
ms.openlocfilehash: 638870376b046f301e6d8b4eb48ae1664db41baeb9c42609ae7d866e606ade13
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53835116"
---
# <a name="network-planning-and-performance-tuning-for-microsoft-365"></a>Microsoft 365 のネットワーク計画とパフォーマンス チューニング
初めて展開するか、Microsoft 365 に移行する前に、これらのトピックの情報を使用して必要な帯域幅を見積もり、Microsoft 365 に展開または移行するのに十分な帯域幅をテストして確認できます。 概要については、「ネットワークと移行の計画」[を参照Microsoft 365。](network-and-migration-planning.md)
  
|カテゴリ |説明 |カテゴリ |説明 |
|:-----|:-----|:-----|:-----|
|**ネットワーク計画** <br/> ![ネットワーク](../media/5e9dcd06-601b-4b28-88dc-f524e7548794.png)           <br/> |すばやく読み込む高速な接続とページが必要ですか?  <br/> 「[ネットワークで最高の接続性とパフォーマンスを得る」をMicrosoft 365。](https://aka.ms/o365perfprinciples)<br/>概[念Microsoft 365については、「ネットワーク接続の概要](microsoft-365-networking-overview.md)」を参照してください。<br/> |**ネットワークの測定** <br/> ![電卓](../media/d690a132-4884-40eb-a918-526bb3dff3cc.png)           <br/> |ベースライン[Microsoft 365パフォーマンス履歴を使用した](performance-tuning-using-baselines-and-history.md)パフォーマンスチューニングと、パフォーマンスのトラブルシューティング計画を参照[Microsoft 365。](performance-troubleshooting-plan.md)  <br/> 既存のネットワークを評価 [するには、次のツールを使用します](network-and-migration-planning.md#calculators)。  <br/> |
|**ベスト プラクティス** <br/> ![ベスト プラクティス](../media/2a659a5c-1007-47d3-a6c6-a19e018ab29b.png)           <br/> |[ネットワーク計画と移行パフォーマンスの向上](network-and-migration-planning.md#BestPractices)に関するベスト プラクティスをMicrosoft 365。 ユーザーを支援する方法を、今すぐ始めてみませんか? 低速[ネットワークでのネットワークの使用Office 365のベスト プラクティスを参照してください](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)。  <br/> [Microsoft 365接続](./microsoft-365-network-connectivity-principles.md)の原則を使用すると、ネットワーク接続を安全に最適化するための最新Microsoft 365理解できます。  <br/> |**Reference** <br/> ![書籍またはジャーナル](../media/56dff3c1-f605-48d8-811f-7d13ce639ecd.png)           <br/> |IP アドレスとポートのリストなど、詳細が必要ですか? 詳細については[、「ネットワーク計画のリファレンス」をMicrosoft 365。](network-and-migration-planning.md#NetReference)  <br/> |
|![Microsoft Cloud Networking for the microsoft Cloud Networking for Enterpriseポスターを参照してください。](../media/3094be9f-2407-4fa5-896d-aa66ef7b9bb9.png)           <br/> |Microsoft Cloud Networking for Microsoft 365およびサービス向けネットワークを最適化する手順については[、「Microsoft Cloud Networking for microsoft Cloud Networking for Enterprise」を参照](../solutions/cloud-architecture-models.md)してください。  <br/> |
   
## <a name="performance-tuning-and-troubleshooting-resources-for-microsoft-365"></a>パフォーマンスの調整とトラブルシューティングに関するリソースをMicrosoft 365
<a name="apptuning"> </a>

展開が完了Microsoft 365、このセクションのトピックを使用してパフォーマンスを最適化できます。 パフォーマンスの低下が発生した場合は、これらのトピックを使用して問題のトラブルシューティングを行います。
  
 **[パフォーマンスOffice 365調整](tune-microsoft-365-performance.md)** する : ネットワーク アドレス変換とネットワーク アドレス変換を使用する方法については、「Office 365 NAT のサポート」を [参照Office 365。](nat-support-with-microsoft-365.md) また、ネットワーク接続の最適化とトラブルシューティングに関するトップ[10 のOffice 365してください](/archive/blogs/onthewire/top-10-tips-for-optimising-troubleshooting-your-office-365-network-connectivity)。 
  
 **[パフォーマンスExchange Online調整](tune-exchange-online-performance.md)** する: これらの記事を使用して、パフォーマンスをExchange Onlineします。 
  
 **[オンラインSkype for Businessのパフォーマンスを調整](tune-skype-for-business-online-performance.md)** する : 次の記事を使用して、オンライン パフォーマンスSkype for Business調整します。 
  
 **[オンラインSharePointのパフォーマンスを調整](tune-sharepoint-online-performance.md)** する: 次の記事を使用して、オンライン パフォーマンスSharePoint調整します。 
  
 **[パフォーマンスProject Online調整](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c)** する : この記事を使用して、パフォーマンスをProject Onlineします。