---
title: Office 365 のネットワークと移行の計画
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: この記事には、ネットワークの計画、テスト、および移行に関する情報へのリンクが含Office 365。
ms.openlocfilehash: aed8bacd4dc08aa6d77ad0c530e721ac9d383bf5
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59210623"
---
# <a name="network-and-migration-planning-for-office-365"></a>Office 365 のネットワークと移行の計画

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

この記事では、ネットワークの計画とテスト、およびネットワークへの移行に関する情報へのOffice 365。
  
初めて展開するか、Office 365 に移行する前に、これらのトピックの情報を使用して必要な帯域幅を見積もり、Office 365 に展開または移行するのに十分な帯域幅をテストして確認できます。

この記事は、ネットワークの計画と[パフォーマンスの調整](./network-planning-and-performance.md)の一部Office 365。

Microsoft Cloud Networking for Microsoft 365およびサービス向けネットワークを最適化する手順については[、「Microsoft Cloud Networking for microsoft Cloud Networking for Enterprise」を参照](../solutions/cloud-architecture-models.md)してください。
   
## <a name="estimate-network-bandwidth-requirements"></a>ネットワーク帯域幅の要件の見積もり
<a name="EstimateBandwidthRequirements"> </a>

このOffice 365使用すると、組織のインターネット回線の使用率が向上する可能性があります。 現在利用可能な帯域幅の量が、Office 365 が完全に展開された後、最も多くの日を処理するために少なくとも 20% の容量を残しながら、予想される増加を処理するのに十分かどうかを判断することが重要です。
  
帯域幅を推定するには、次の手順を使用します。
  
1. 各インターネット出力を使用するクライアントの数を評価します。 マルチテラビット ネットワークで可能な限り多くの接続を処理します。 
    
2. クライアントがOffice 365するサービスと機能を決定します。 サービスや利用状況プロファイルが異なるユーザーのグループがある可能性があります。
    
3. クライアントのパイロット グループのネットワーク使用を測定します。 パイロット クライアントが組織内のユーザーの異なるプロファイルと、さまざまな地理的な場所を表す必要があります。 結果を、古い計算機とクロスチェックして、ExchangeとMicrosoft Teams、独自のネットワーク[](/microsoftteams/prepare-network)で実行したケース スタディ[](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)を確認できます。 [](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744) 
    
4. パイロット グループの測定値を使用して、組織のニーズ全体を推定し、ネットワークに変更を加える前に、見積もりを検証するために再テストします。
    
## <a name="test-your-existing-network"></a>既存のネットワークをテストする
<a name="calculators"> </a>

 **ネットワーク ツール。** インターネット帯域幅をテストして検証し、ダウンロード、アップロード、遅延の制約を判断します。 これらのツールは、完全に展開した後と同様に、移行のためのネットワークの機能を判断するのに役立ちます。 
    
- [Microsoft Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=517243): 環境内の接続Exchange Onlineテストします。
    
- Microsoft サポート/回復アシスタント[を使用Office 365](https://diagnostics.office.com/#/Download?env=SOC)問題Outlook解決Office 365してください。 
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a>ネットワーク計画と移行パフォーマンスの向上に関するベスト プラクティスは、Office 365
<a name="BestPractices"> </a>

エクスペリエンスの向上に関する詳細については、これらのベスト プラクティスについて詳Office 365してください。
  
1. ユーザーを支援する方法を、今すぐ始めてみませんか? ネットワーク[が](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)連携していないSharePoint Online、Exchange Online、Lync Online などの Office 365 の使用に関するヒントについては、「低速ネットワークで Office 365 を使用するためのベスト プラクティス」を参照してください。 この記事では、Office 365 エクスペリエンスを最適化するための TechNet と Support.office.com のコンテンツの負荷にリンクし、web ページをカスタマイズする簡単な方法と、Office 365 エクスペリエンスを最大限に活用するために Internet Explorer 設定を設定する方法について説明します。 
    
2. ネットワーク[Office 365の](./microsoft-365-network-connectivity-principles.md)原則を参照して、トラフィックを安全に管理し、可能な限り最高のパフォーマンスを得Office 365接続の原則を理解してください。 この記事では、Office 365 ネットワーク接続をセキュリティで保護するための最新のガイドについて説明します。 
    
3. 更新プログラムのスケジュールを慎重に管理することで、メールWindows向上します。 クライアント コンピューターをバッチで更新し、ネットワーク帯域幅の使用を調整するために Office 365 に移行する前に、すべてのクライアント コンピューターが更新されます。 詳細については、「最新の更新プログラムのデスクトップを手動で更新および構成[Office 365を参照してください](https://support.microsoft.com/gp/office-2013-365-update)。
    
4. Office 365ネットワーク トラフィックは、信頼できるインターネット サービスとして扱い、一部の組織が信頼されていないインターネット サービスへのネットワーク トラフィックに配置する従来のフィルター処理とスキャンの多くをバイパスできる場合に最適です。 これには、通常、プロキシ ユーザー認証やパケット 検査などの送信処理を削除し、ネットワーク アドレス変換 (NAT) を適切に使用してインターネットへのローカル出力を確保し、増加するネットワーク要求を処理するのに十分な帯域幅容量が含まれます。 ネットワーク上の[信頼Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)インターネット サービスとしてネットワークを処理するためのネットワークの構成に関するOffice 365詳細については、「ネットワーク エンドポイントの管理」を参照してください。
    
1. [[エンドポイントのOffice 365する] を確認します](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)。 追加のトラフィックがOffice 365、送信プロキシ接続が増加し、TLS/SSL を使用したセキュリティで保護されたトラフィックが増加します。
    
2. 送信プロキシでユーザー認証が必要な場合は、接続が遅くなるか、機能が失われる可能性があります。 ドメインの認証要件をバイパスOffice 365このオーバーヘッドを削減できます。
    
3. 共有予定表とメールボックスの数が多い場合は、ユーザーからユーザーへの接続数がOutlook Exchange。 たとえば、クライアントは、Outlook共有予定表ごとに最大 2 つの追加接続を開く可能性があります。 この状況では、出力プロキシが接続を処理できるか、またはプロキシをバイパスして、Office 365接続Outlook。
    
4. パブリック IP アドレスでサポートされるデバイスの最大数と、複数の IP アドレス間で負荷分散する方法を決定します。 詳細については、[Office 365 の NAT サポート](nat-support-with-microsoft-365.md)をご覧ください。
    
5. ネットワーク上のコンピューターからの送信接続を検査する場合は、このフィルターを Office 365 ドメインにバイパスすると、接続とパフォーマンスが向上します。 さらに、多くの場合、送信検査をバイパスすると、単一のインターネット出力が不要になる場合が多く、ネットワーク要求に対するローカル インターネット出力Office 365有効にできます。
    
6. 一部のお客様は、内部ネットワーク設定がパフォーマンスに影響を与える可能性があります。 設定伝送ユニット (MTU) の最大サイズ、ネットワークの自動ネゴシエーションまたは自動検出、インターネットへの最適なルートなど、一般的な場所です。
    
## <a name="network-planning-reference-for-office-365"></a>ネットワーク計画に関するOffice 365
<a name="NetReference"> </a>

これらのトピックには、ネットワーク参照Office 365詳細な情報が含まれています。
  
- [Office 365 エンドポイントの管理](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [コンテンツ配信ネットワーク](content-delivery-networks.md)
    
- [Office 365 の外部ドメイン ネーム システムのレコード](external-domain-name-system-records.md)
    
- [Office 365 サービスでの IPv6 サポート](ipv6-support.md)
    
- [Office 365 ネットワーク接続の原則](./microsoft-365-network-connectivity-principles.md)
    
- [Office 365 サービスに接続するネットワーク デバイスの計画](plan-for-network-devices.md)
    
- [サービスのセットアップ Office 365ガイド](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)