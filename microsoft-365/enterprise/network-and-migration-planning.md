---
title: Office 365 のネットワークと移行の計画
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 6/29/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
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
description: この記事には、ネットワークの計画、テスト、およびOffice 365への移行に関する情報へのリンクが含まれています。
ms.openlocfilehash: 6288c9afae66206b7284f751f8a63381ab8451e8
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65077458"
---
# <a name="network-and-migration-planning-for-office-365"></a>Office 365 のネットワークと移行の計画

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

この記事には、ネットワークの計画とテスト、およびOffice 365への移行に関する情報へのリンクが含まれています。
  
初めてデプロイするか、Office 365に移行する前に、これらのトピックの情報を使用して必要な帯域幅を見積もり、Office 365にデプロイまたは移行するのに十分な帯域幅があることをテストして確認できます。

この記事は、[Office 365のネットワーク計画とパフォーマンスのチューニングの](./network-planning-and-performance.md)一部です。

Microsoft 365およびその他の Microsoft クラウド プラットフォームとサービスに対してネットワークを最適化する手順については、「[Microsoft Cloud Networking for Enterprise Architects](../solutions/cloud-architecture-models.md)」のポスターを参照してください。
   
## <a name="estimate-network-bandwidth-requirements"></a>ネットワーク帯域幅の要件を見積もる
<a name="EstimateBandwidthRequirements"> </a>

Office 365を使用すると、組織のインターネット回線の使用率が向上する可能性があります。 現在使用可能な帯域幅の量が、Office 365が完全にデプロイされた後、最も混雑した日数を処理するために少なくとも 20% の容量を残しながら、推定増加を処理するのに十分かどうかを判断することが重要です。
  
帯域幅を見積もるには、次の手順に従います。
  
1. 各インターネット エグレスを使用するクライアントの数を評価します。 マルチテラビット ネットワークが可能な限り多くの接続を処理できるようにします。 
    
2. クライアントが使用できるOffice 365サービスと機能を決定します。 サービスや使用状況プロファイルが異なるユーザーのグループが含まれている可能性があります。
    
3. クライアントのパイロット グループに対するネットワークの使用を測定します。 パイロット クライアントが組織内のさまざまなプロファイルと、さまざまな地理的場所を代表していることを確認します。 Exchangeと[Microsoft Teams](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744)、または自社のネットワークで実行した[ケース スタディ](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)について、古い計算[](/microsoftteams/prepare-network)ツールに対して結果をクロスチェックできます。 
    
4. パイロット グループの測定値を使用して組織全体のニーズを推定し、再テストして見積もりを検証してから、ネットワークに変更を加えます。
    
## <a name="test-your-existing-network"></a>既存のネットワークをテストする
<a name="calculators"> </a>

 **ネットワーク ツール。** インターネット帯域幅をテストして検証し、ダウンロード、アップロード、待機時間の制約を決定します。 これらのツールは、完全にデプロイした後だけでなく、移行のためのネットワークの機能を決定するのに役立ちます。 
    
- [Microsoft Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=517243): Exchange Online環境での接続をテストします。
    
- [Office 365のMicrosoft サポートと回復アシスタントを使用して、Outlook](https://diagnostics.office.com/#/Download?env=SOC)とOffice 365の問題を解決します。 

- [Microsoft 365ネットワーク接続テスト ツール: ネットワーク接続](/microsoft-365/enterprise/office-365-network-mac-perf-onboarding-tool)Microsoft 365テストします。
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a>Office 365のネットワーク計画と移行パフォーマンスの向上に関するベスト プラクティス
<a name="BestPractices"> </a>

Office 365エクスペリエンスを向上させる方法の詳細については、これらのベスト プラクティスについてもう少し詳しく説明します。
  
1. すぐにユーザーのサポートを開始しますか? SharePoint Online、Exchange Online、Lync Online など、ネットワークが協力していない場合のOffice 365の使用方法については、低速ネットワークでのOffice 365の使用に関する[ベスト プラクティス](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)に関するページを参照してください。 この記事では、Office 365 エクスペリエンスを最適化するための TechNet と Support.office.com のコンテンツの読み込みと、Web ページを簡単にカスタマイズする方法と、最適なOffice 365エクスペリエンスのために Internet Explorer の設定を設定する方法に関する情報が含まれています。 
    
2. [Office 365ネットワーク接続の原則](./microsoft-365-network-connectivity-principles.md)に関する記事を参照して、Office 365 トラフィックを安全に管理し、可能な限り最高のパフォーマンスを得るための接続の原則を理解してください。 この記事では、Office 365 ネットワーク接続をセキュリティで保護するための最新のガイドについて説明します。 
    
3. Windows更新プログラムのスケジュールを慎重に管理することで、メール移行のパフォーマンスを向上させます。 クライアント コンピューターをバッチで更新し、ネットワーク帯域幅の使用を規制するためにOffice 365に移行する前にすべてのクライアント コンピューターが更新されていることを確認できます。 詳細については、「[最新の更新プログラムのOffice 365用にデスクトップを手動で更新して構成する」を](https://support.microsoft.com/gp/office-2013-365-update)参照してください。
    
4. Office 365ネットワーク トラフィックは、信頼されたインターネット サービスとして扱われ、一部の組織が信頼されていないインターネット サービスへのネットワーク トラフィックに配置する従来のフィルター処理とスキャンの多くをバイパスできる場合に最適です。 これには通常、プロキシ ユーザー認証やパケット検査などの送信処理を削除するだけでなく、ネットワーク アドレス変換 (NAT) が適切で、増加するネットワーク要求を処理するのに十分な帯域幅容量を使用してインターネットへのローカルエグレスを確保することが含まれます。 ネットワーク上[の](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)信頼されたインターネット サービスとしてOffice 365を処理するようにネットワークを構成する方法については、「Office 365 エンドポイントの管理」を参照してください。
    
1. [エンドポイントOffice 365管理していることを確認します](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)。 追加のトラフィックがOffice 365すると、送信プロキシ接続が増加し、TLS/SSL 経由のセキュリティで保護されたトラフィックが増加します。
    
2. 送信プロキシでユーザー認証が必要な場合は、接続が遅くなったり、機能が失われたりすることがあります。 Office 365 ドメインの認証要件をバイパスすると、このオーバーヘッドを減らすことができます。
    
3. 共有予定表とメールボックスの数が多い場合は、OutlookからExchangeへの接続数が増加することがあります。 たとえば、Outlook クライアントは、使用中の共有予定表ごとに最大 2 つの追加接続を開く場合があります。 このような場合は、エグレス プロキシが接続を処理できることを確認するか、OutlookのOffice 365への接続にプロキシをバイパスします。
    
4. パブリック IP アドレスでサポートされているデバイスの最大数と、複数の IP アドレス間で負荷分散する方法を決定します。 詳細については、[Office 365 の NAT サポート](nat-support-with-microsoft-365.md)をご覧ください。
    
5. ネットワーク上のコンピューターからの送信接続を検査する場合、このフィルター処理をOffice 365 ドメインにバイパスすると、接続とパフォーマンスが向上します。 さらに、送信検査をバイパスすると、多くの場合、単一のインターネット エグレスが不要になり、Office 365宛先ネットワーク要求に対してローカル インターネット エグレスが有効になります。
    
6. 一部のお客様は、内部ネットワーク設定がパフォーマンスに影響を与える可能性があることがわかります。 最大伝送単位 (MTU) サイズ、ネットワーク自動ネゴシエーションまたは自動検出、インターネットへの最適でないルートなどの設定は、一般的な場所です。
    
## <a name="network-planning-reference-for-office-365"></a>Office 365のネットワーク計画リファレンス
<a name="NetReference"> </a>

これらのトピックには、詳細なOffice 365ネットワーク参照情報が含まれています。
  
- [Office 365 エンドポイントの管理](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [コンテンツ配信ネットワーク](content-delivery-networks.md)
    
- [Office 365 の外部ドメイン ネーム システムのレコード](external-domain-name-system-records.md)
    
- [Office 365 サービスでの IPv6 サポート](ipv6-support.md)
    
- [Office 365 ネットワーク接続の原則](./microsoft-365-network-connectivity-principles.md)
    
- [Office 365 サービスに接続するネットワーク デバイスの計画](plan-for-network-devices.md)
    
- [Office 365 サービスのセットアップ ガイド](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)
