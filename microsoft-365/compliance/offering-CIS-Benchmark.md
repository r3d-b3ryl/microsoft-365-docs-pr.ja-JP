---
title: Center for Internet Security (CIS) ベンチマーク
description: Center for Internet Security (CIS) は、Microsoft の製品とサービスに関する一連のベンチマークを公開しています
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: 968e2196bec0ff853c8f68625ca078f384d8951d
ms.sourcegitcommit: b2197dbf723d11992bbad568a84df3ef3cff421d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "39233610"
---
# <a name="compliance-offering-center-for-internet-security-cis-benchmarks"></a>コンプライアンスの提供: Center for Internet Security (CIS) ベンチマーク

## <a name="about-cis-benchmarks"></a>CIS ベンチマークについて

[Center for Internet Security](https://www.cisecurity.org/) は、“サイバー防衛のためのベスト プラクティス ソリューションを特定、開発、検証、促進、維持する” ことを使命とする非営利団体です。 世界中の政府、企業、学術界のサイバーセキュリティおよび IT の専門家が持つ専門知識を活用しています。 CIS ベンチマーク、コントロール、ハードニング済みイメージなどを含む標準およびベスト プラクティスを開発するために、コンセンサス意思決定モデルに従います。  
  
[CIS ベンチマーク](https://www.cisecurity.org/cis-benchmarks/)は、システムを安全に構成するための構成基準およびベスト プラクティスです。 各ガイダンスの推奨事項は、組織のサイバー防衛機能の向上を支援するために開発された 1 つ以上の [CIS コントロール](https://www.cisecurity.org/controls/)を参照しています。 CIS コントロールは、NIST Cybersecurity Framework (CSF) および NIST SP 800-53、ISO 27000 シリーズの規格、PCI DSS、HIPAA などを含む多くの確立された規格および規制の枠組みに対応しています。  
  
各ベンチマークは、コンセンサス レビューの 2 つのフェーズを経由します。 1 つ目は最初の開発中で、専門家が召集され作業用ドラフトについて議論し、作成し、テストをし、ベンチマークに関する合意に達するまで行われます。 ベンチマークが公開された後の第 2 フェーズでは、コンセンサス チームがインターネット コミュニティからのフィードバックをベンチマークに組み込むために確認します。  
  
CIS ベンチマークは、2 つのレベルのセキュリティ設定を提供します。

- **レベル 1** では、あらゆるシステムで構成でき、サービスの中断や機能の低下をほとんど、またはまったく引き起こさない、不可欠となる基本セキュリティ要件を推奨しています。
- **レベル 2** では、機能の低下を引き起こす可能性のある、より高度なセキュリティを必要とする環境向けのセキュリティ設定を推奨しています。

[CIS ハードニング済みイメージ](https://www.cisecurity.org/blog/cis-hardened-images-now-in-microsoft-azure-marketplace/) は、レベル 1 またはレベル 2 CIS ベンチマーク プロファイルへとハードニングされた CIS ベンチマークに基づき、安全に構成された仮想マシン イメージです。 ハードニングとは、システムをサイバー攻撃に対して脆弱にする潜在的な脆弱性を制限することにより、不正アクセス、サービス拒否 (DoS 攻撃)、およびその他のサイバー脅威からの保護を支援するプロセスです。

## <a name="microsoft-and-the-cis-benchmarks"></a>Microsoft と CIS ベンチマーク

Center for Internet Security (CIS) は、Microsoft Azure および Microsoft 365 基礎ベンチマーク、Windows 10 ベンチマーク、Windows Server 2016 ベンチマークなどを含む Microsoft 製品およびサービスのベンチマークを公開しています。  
  
CIS ベンチマークは、IT システムおよびデータをサイバー攻撃から守るためのセキュリティ規格として国際的に認められています。 何千もの企業で採用され、安全なベースライン構成を確立するための規範的なガイダンスを提供します。 システムおよびアプリケーションの管理者、セキュリティ スペシャリスト、および Microsoft 製品とサービスを使用してソリューションを開発するその他のユーザーは、これらのベスト プラクティスを使用してアプリケーションのセキュリティを評価および改善することができます。  
  
すべての CIS ベンチマークと同様に Microsoft ベンチマークは、ソフトウェア開発、監査とコンプライアンス、セキュリティ研究、運用、政府、法律に及ぶさまざまなバックグラウンドを持つ内容領域専門家からの情報提供に基づくコンセンサス レビュー プロセスを使用して作成されました。 Microsoft は、これらの CIS の取り組みにおいて不可欠なパートナーでした。 たとえば、リストされたサービスに対して Office 365 がテストされ、その結果となる Microsoft 365 基礎ベンチマークは、アカウントと認証、データ管理、アプリケーションのアクセス許可、ストレージ、およびその他のセキュリティ ポリシー領域を対象とした適切なセキュリティ ポリシーを設定するための幅広い推奨事項をカバーしています。  
  
CIS は、Microsoft 製品およびサービスのベンチマークに加えて、CIS ベンチマークを満たすように構成された [Azure 仮想マシンでの使用するための CIS ハードニング済みイメージ](https://www.cisecurity.org/blog/cis-hardened-images-now-in-microsoft-azure-marketplace/)も公開しています。 それらには、Azure 上での実行が保証された Microsoft Windows Server 2016 向け CIS ハードニング済みイメージが含まれます。 CIS は次のように述べています。 “[Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/apps?search=center%20for%20internet%20security) で利用可能なすべての CIS ハードニング済みイメージは、Azure での実行が保証されています。 Azure パブリック クラウド、クラウド OS ネットワークを介してサービス プロバイダーがホストする Microsoft クラウド プラットフォーム、およびお客様が管理するオンプレミスのプライベート クラウド Windows Server Hyper-V 展開への用意および互換性については、事前にテストをしています。”

## <a name="microsoft-in-scope-cloud-services"></a>対象となる Microsoft のクラウド サービス

- [Azure および Azure Government](https://aka.ms/AzureCompliance)
- [Office および Microsoft 365](https://aka.ms/o365-compliance-framework)
- SQL Server
- Windows 10
- Windows Server 2016

## <a name="audits-reports-and-certificates"></a>監査、レポート、証明書

Microsoft 製品およびサービスの [CIS ベンチマークの全ての一覧](https://www.cisecurity.org/cis-benchmarks/)を入手してください。

- [CIS Azure 基礎ベンチマーク](https://www.cisecurity.org/benchmark/azure/)
- [CIS Microsoft 365 基礎ベンチマーク](https://www.cisecurity.org/benchmark/microsoft_office/)
- [Windows 10 ベンチマーク](https://www.cisecurity.org/benchmark/microsoft_windows_desktop/)
- [Windows Server 2016 ベンチマーク](https://www.cisecurity.org/benchmark/microsoft_windows_server/)

## <a name="how-to-implement"></a>実装方法

- [Azure 向け CIS ベンチマーク](https://azure.microsoft.com/mediahandler/files/resourcefiles/cis-microsoft-azure-foundations-security-benchmark/CIS_Microsoft_Azure_Foundations_Benchmark_v1.0.0.pdf): Azure の安全なベースライン構成を確立するための規範的なガイダンスを入手してください。  
- [Office 365 セキュリティ ロードマップ](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap): このロードマップに従うことにより、データ漏えいまたはアカウント侵害の可能性を最小限に抑えます。
- [Windows セキュリティ ベースライン](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines): 組織内でセキュリティ ベースラインを効果的に使用するには、これらのガイドラインに従ってください。
- [CIS Controls クラウド コンパニオン ガイド](https://www.cisecurity.org/white-papers/cis-controls-cloud-companion-guide/): CIS Controls バージョン 7 のセキュリティ ベスト プラクティスをクラウド環境に適用するためのガイダンスを入手してください。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**CIS ベンチマーク設定に準拠することにより、アプリケーションのセキュリティは確保されますか ?**

CIS ベンチマークは、対象となる Microsoft 製品およびサービスを採用しているすべてのユーザーに基礎レベルのセキュリティを確立します。 ただし、これらはすべての考えうるセキュリティ構成およびアーキテクチャを網羅したリストとしてではなく、出発点として見なされなければなりません。 各組織は、特定の状況、ワークロード、コンプライアンス要件を引き続き評価し、それに応じて環境を調整する必要があります。

**CIS ベンチマークはどの程度の頻度で更新されますか ?**

改訂された CIS ベンチマークのリリースは、それを開発した IT プロフェッショナルのコミュニティ、およびベンチマークがサポートするテクノロジーのリリース スケジュールに応じて変わってきます。 CIS は、新しいベンチマークおよび既存のベンチマークの更新を発表する月次レポートを配布します。 これらを受け取るには [CIS Workbench](https://workbench.cisecurity.org/) に登録し (無料)、プロフィール画面の [ニュースレターを受け取る] をオンにします。

**Microsoft CIS ベンチマークの開発に貢献したのは誰ですか ?**

CIS は、“ベンチマークは内容領域専門家、テクノロジー ベンダー、パブリックおよびプライベートの CIS ベンチマーク コミュニティ メンバー、および CIS ベンチマーク開発チームの惜しみないボランティア活動によって開発されています。” と述べています。 たとえば、「[CIS Microsoft Azure 基礎ベンチマーク v1.0.0 が公開されました (CIS Microsoft Azure Foundations Benchmark v1.0.0 Now Available)](https://www.cisecurity.org/blog/cis-microsoft-azure-foundations-benchmark-v1-0-0-now-available/)」で Azure の貢献者の一覧を見つけることができます。

## <a name="resources"></a>リソース

- [Microsoft 365 を安全に使用するための CIS ベスト プラクティス](https://www.microsoft.com/security/blog/2019/01/10/best-practices-for-securely-using-microsoft-365-the-cis-microsoft-365-foundations-benchmark-now-available/)
- [Windows 10 のセキュリティ ポリシー設定](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/security-policy-settings)
- [Windows 10 Enterprise のセキュリティ](https://docs.microsoft.com/windows/security/index)
- [Microsoft Trust Center のコンプライアンス](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>サービスの背景資料をダウンロードする

このサービスに関する背景資料が必要ですか? [PDF](https://download.microsoft.com/download/9/B/7/9B75D846-BDB9-41CB-86FF-F0ADFD15800B/CIS_Benchmarks-Compliance.pdf) をダウンロードします。
