---
title: Microsoft 365 のネットワーク計画とパフォーマンス チューニング
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 2/18/2022
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Strat_O365_Enterprise
f1.keywords:
- CSH
search.appverid:
- MET150
ms.assetid: e5f1228c-da3c-4654-bf16-d163daee8848
ms.custom:
- seo-marvel-apr2020
- Adm_O365
description: この記事は、Microsoft 365のネットワーク帯域幅要件を計画し、パフォーマンスを微調整してトラブルシューティングするのに役立ちます。
ms.openlocfilehash: 628d532a106ce9776443b252c863fa8bdc221b4b
ms.sourcegitcommit: bb493f12701f6d6ee7d5e64b541adb87470bc7bc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2022
ms.locfileid: "62900772"
---
# <a name="network-planning-and-performance-tuning-for-microsoft-365"></a>Microsoft 365 のネットワーク計画とパフォーマンス チューニング
初めてデプロイするか、Microsoft 365に移行する前に、これらのトピックの情報を使用して必要な帯域幅を見積もり、Microsoft 365にデプロイまたは移行するのに十分な帯域幅があることをテストして確認できます。 概要については、「[Microsoft 365のネットワークと移行の計画」を](network-and-migration-planning.md)参照してください。
  
|カテゴリ |説明 |カテゴリ |説明 |
|:-----|:-----|:-----|:-----|
|**ネットワーク計画** <br/> ![ネットワーク。](../media/5e9dcd06-601b-4b28-88dc-f524e7548794.png)           <br/> |すばやく読み込む高速接続とページが必要ですか?  <br/> [Microsoft 365での最適な接続とパフォーマンスの取得に関する記事を参照してください](https://aka.ms/o365perfprinciples)。<br/>概念Microsoft 365理解するには[、「ネットワーク接続の概要](microsoft-365-networking-overview.md)」を参照してください。<br/> |**ネットワークの測定** <br/> ![計算機](../media/d690a132-4884-40eb-a918-526bb3dff3cc.png)           <br/> |[Microsoft 365のベースラインとパフォーマンス履歴とパフォーマンス](performance-tuning-using-baselines-and-history.md)[のトラブルシューティング 計画を使用したパフォーマンスチューニングMicrosoft 365](performance-troubleshooting-plan.md)読み取ります。  <br/> これらのツールを使用して [、既存のネットワークを評価します](network-and-migration-planning.md#calculators)。  <br/> |
|**ベスト プラクティス** <br/> ![ベスト プラクティス。](../media/2a659a5c-1007-47d3-a6c6-a19e018ab29b.png)           <br/> |[Microsoft 365のネットワーク計画と移行パフォーマンスの向上に関するベスト プラクティス](network-and-migration-planning.md#BestPractices)。 すぐにユーザーのサポートを開始しますか? [低速ネットワークでOffice 365を使用するためのベスト プラクティスを](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)参照してください。  <br/> [Microsoft 365ネットワーク接続の原則](./microsoft-365-network-connectivity-principles.md)は、ネットワーク接続を安全に最適化するための最新のガイダンスMicrosoft 365理解するのに役立ちます。  <br/> |**Reference** <br/> ![書籍または日誌](../media/56dff3c1-f605-48d8-811f-7d13ce639ecd.png)           <br/> |IP アドレスとポートの一覧など、詳細が必要ですか? Microsoft 365については、[ネットワーク計画のリファレンスを](network-and-migration-planning.md#NetReference)参照してください。  <br/> |
|![microsoft Cloud Networking for Enterprise Architects のポスターを参照してください。](../media/3094be9f-2407-4fa5-896d-aa66ef7b9bb9.png)           <br/> |Microsoft 365およびその他の Microsoft クラウド プラットフォームとサービスに対してネットワークを最適化する手順については、「[Microsoft Cloud Networking for Enterprise Architects](../solutions/cloud-architecture-models.md)」のポスターを参照してください。  <br/> |
   
## <a name="performance-tuning-and-troubleshooting-resources-for-microsoft-365"></a>Microsoft 365のパフォーマンスチューニングとトラブルシューティングリソース
<a name="apptuning"> </a>

デプロイMicrosoft 365したら、このセクションのトピックを使用してパフォーマンスを最適化できます。 パフォーマンスの低下が発生した場合は、これらのトピックを使用して問題のトラブルシューティングを行うこともできます。
  
 **[Office 365パフォーマンスを調整](tune-microsoft-365-performance.md)** する: Office 365でネットワーク アドレス変換を使用する方法については、「[Office 365での NAT サポート](nat-support-with-microsoft-365.md)」を参照してください。 また、[Office 365ネットワーク接続の最適化とトラブルシューティングに関するトップ 10 のヒントもご確認ください](/archive/blogs/onthewire/top-10-tips-for-optimising-troubleshooting-your-office-365-network-connectivity)。
  
 **[Exchange Onlineパフォーマンスを調整](tune-exchange-online-performance.md)** する: これらの記事を使用して、Exchange Onlineパフォーマンスを微調整します。

 **[Microsoft Teamsのために組織のネットワークを準備](/microsoftteams/prepare-network)** する: これらの記事を使用して、Teams用にネットワークを最適化します。
  
 **[オンライン パフォーマンスSkype for Business調整](tune-skype-for-business-online-performance.md)** する: これらの記事を使用して、オンライン パフォーマンスSkype for Business微調整します。
  
 **[オンライン パフォーマンスSharePoint調整](tune-sharepoint-online-performance.md)** する: これらの記事を使用して、オンライン パフォーマンスSharePoint微調整します。
  
 **[Project Onlineパフォーマンスを調整する](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c)**: この記事を使用してパフォーマンスを微調整Project Online
