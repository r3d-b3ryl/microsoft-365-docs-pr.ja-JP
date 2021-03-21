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
description: この記事には、ネットワークの計画、テスト、および 365 への移行に関するOfficeがあります。
ms.openlocfilehash: 99bcc1bd0447b192860fc0bcc67fc18d87c2d5fc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923590"
---
# <a name="network-and-migration-planning-for-office-365"></a>Office 365 のネットワークと移行の計画

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

この記事には、ネットワークの計画とテスト、および 365 への移行に関するOfficeがあります。
  
初めて展開するか、Office 365 に移行する前に、これらのトピックの情報を使用して必要な帯域幅を見積もり、Office 365 に展開または移行するのに十分な帯域幅をテストして確認できます。

この記事は [、365](./network-planning-and-performance.md)のネットワーク計画とパフォーマンスの調整Officeです。

Microsoft 365 および他の Microsoft クラウド プラットフォームとサービスのネットワークを最適化する手順については [、「Microsoft Cloud Networking for Enterprise Architects」](../solutions/cloud-architecture-models.md) ポスターを参照してください。
   
## <a name="estimate-network-bandwidth-requirements"></a>ネットワーク帯域幅の要件の見積もり
<a name="EstimateBandwidthRequirements"> </a>

365 Officeを使用すると、組織のインターネット回線の使用率が向上する可能性があります。 Office 365 が完全に展開された後、最も多くの日数を処理するために少なくとも 20% の容量を残しながら、現在利用可能な帯域幅の量が予想される増加を処理するのに十分かどうかを判断することが重要です。
  
帯域幅を推定するには、次の手順を使用します。
  
1. 各インターネット出力を使用するクライアントの数を評価します。 マルチテラビット ネットワークで可能な限り多くの接続を処理します。 
    
2. クライアントがOffice 365 のサービスと機能を決定します。 サービスや利用状況プロファイルが異なるユーザーのグループがある可能性があります。
    
3. クライアントのパイロット グループのネットワーク使用を測定します。 パイロット クライアントが組織内のユーザーの異なるプロファイルと、さまざまな地理的な場所を表す必要があります。 Exchange と[Microsoft Teams](/microsoftteams/prepare-network)の古い計算機、[](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744)または独自のネットワークで実行[](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)したケース スタディに対して、結果をクロスチェックできます。 
    
4. パイロット グループの測定値を使用して、組織のニーズ全体を推定し、ネットワークに変更を加える前に、見積もりを検証するために再テストします。
    
## <a name="test-your-existing-network"></a>既存のネットワークをテストする
<a name="calculators"> </a>

 **ネットワーク ツール。** インターネット帯域幅をテストして検証し、ダウンロード、アップロード、遅延の制約を判断します。 これらのツールは、完全に展開した後と同様に、移行のためのネットワークの機能を判断するのに役立ちます。 
    
- [Microsoft リモート接続アナライザー](https://go.microsoft.com/fwlink/p/?LinkId=517243): Exchange Online 環境での接続をテストします。
    
- Outlook および [365 の問題を解決するには、Office 365](https://diagnostics.office.com/#/Download?env=SOC) の Microsoft サポート Officeアシスタントを使用します。 
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a>365 のネットワーク計画と移行パフォーマンスの向上Office方法
<a name="BestPractices"> </a>

365 エクスペリエンスの向上に関する詳細については、これらのベスト プラクティスOffice詳しくはお読みください。
  
1. ユーザーを支援する方法を、今すぐ始めてみませんか? ネットワークが連携していない場合の Office 365 (SharePoint Online、Exchange Online、Lync Online など) の使用に関するヒントについては、「低速ネットワークで [Office 365](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) を使用するためのベスト プラクティス」を参照してください。 この記事では、Office 365 エクスペリエンスを最適化するための TechNet と Support.office.com のコンテンツの負荷にリンクし、web ページをカスタマイズする簡単な方法と、Office 365 エクスペリエンスの最適な Internet Explorer 設定を設定する方法について説明します。 
    
2. [365 Office 365](./microsoft-365-network-connectivity-principles.md)ネットワーク接続の原則を参照して、365 トラフィックを安全に管理し、可能な限り最高のパフォーマンスを得Office接続の原則を理解してください。 この記事では、Office 365 ネットワーク接続をセキュリティで保護するための最新のガイドについて説明します。 
    
3. Windows 更新プログラムのスケジュールを慎重に管理することで、メール移行のパフォーマンスを向上させます。 クライアント コンピューターをバッチで更新し、すべてのクライアント コンピューターが Office 365 に移行する前に更新され、ネットワーク帯域幅の使用を調整できます。 詳細については、「最新の更新プログラムについては、デスクトップを手動で更新Office [365 用に構成する」を参照してください](https://support.microsoft.com/gp/office-2013-365-update)。
    
4. Office 365 ネットワーク トラフィックは、信頼できるインターネット サービスとして扱い、一部の組織が信頼されていないインターネット サービスへのネットワーク トラフィックに配置する従来のフィルター処理とスキャンの多くをバイパスできる場合に最適です。 これには、通常、プロキシ ユーザー認証やパケット 検査などの送信処理を削除し、ネットワーク アドレス変換 (NAT) を適切に使用してインターネットへのローカル出力を確保し、増加するネットワーク要求を処理するのに十分な帯域幅容量が含まれます。 Office [365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)をネットワーク上の信頼できるインターネット サービスとして処理するためのネットワークの構成に関するその他のガイダンスについては、「365 エンドポイントの管理」を参照 Officeしてください。
    
1. [365 Officeの管理を確認します](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)。 365 を使用するOfficeすると、送信プロキシ接続が増加し、TLS/SSL 上のセキュリティで保護されたトラフィックが増加します。
    
2. 送信プロキシでユーザー認証が必要な場合は、接続が遅くなるか、機能が失われる可能性があります。 365 ドメインの認証要件をOfficeすると、このオーバーヘッドを削減できます。
    
3. 共有予定表とメールボックスの数が多い場合は、Outlook から Exchange への接続数が増える場合があります。 たとえば、Outlook クライアントは、使用している共有予定表ごとに最大 2 つの追加接続を開く場合があります。 この状況では、出力プロキシが接続を処理したり、Outlook 用の 365 への接続Officeバイパスしたりできます。
    
4. パブリック IP アドレスでサポートされるデバイスの最大数と、複数の IP アドレス間で負荷分散する方法を決定します。 詳細については、[Office 365 の NAT サポート](nat-support-with-microsoft-365.md)をご覧ください。
    
5. ネットワーク上のコンピューターからの送信接続を検査する場合は、このフィルター処理を Office 365 ドメインにバイパスすると、接続性とパフォーマンスが向上します。 さらに、多くの場合、送信検査をバイパスすると、単一のインターネット出力が不要になる場合が多く、365 件のネットワーク要求に対してローカルOfficeを有効にできます。
    
6. 一部のお客様は、内部ネットワーク設定がパフォーマンスに影響を与える可能性があります。 最大伝送単位 (MTU) サイズ、ネットワークの自動ネゴシエーションまたは自動検出、インターネットへの最適なルートの設定は、一般的な場所です。
    
## <a name="network-planning-reference-for-office-365"></a>365 のネットワーク計画Office参照
<a name="NetReference"> </a>

これらのトピックには、365 ネットワークOffice詳細な情報が含まれています。
  
- [Office 365 エンドポイントの管理](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [コンテンツ配信ネットワーク](content-delivery-networks.md)
    
- [Office 365 の外部ドメイン ネーム システムのレコード](external-domain-name-system-records.md)
    
- [Office 365 サービスでの IPv6 サポート](ipv6-support.md)
    
- [Office 365 ネットワーク接続の原則](./microsoft-365-network-connectivity-principles.md)
    
- [Office 365 ビデオ ネットワークに関するよく寄せられる質問 (FAQ)](office-365-video-networking-faq.md)
    
- [Office 365 サービスに接続するネットワーク デバイスの計画](plan-for-network-devices.md)
    
- [365 サービスのOfficeガイド](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)