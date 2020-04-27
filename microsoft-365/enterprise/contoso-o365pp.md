---
title: Contoso 社の Microsoft 365 Apps for enterprise の展開
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社が Microsoft Endpoint Configuration Manager を使用して Microsoft 365 Apps for enterprise を展開する方法について説明します。
ms.openlocfilehash: eca3978103ca1e590d747b3549a3c9e393f871ca
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43625256"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>Contoso 社の Microsoft 365 Apps for enterprise の展開

Contoso 社では自社の PC を Windows 10 Enterprise と Microsoft 365 Apps for enterprise にアップグレードして、これまで以上に効果的な共同作業、セキュリティの向上、および最新のデスクトップ エクスペリエンスを実現しました。インフラストラクチャとビジネス ニーズを評価した後、Contoso 社は展開に向けて、以下の重要な要件を特定しました。

- すべての PC が Microsoft 365 Apps for enterprise を実行する必要があります
- 可能な場合は、既存の管理ツールとインフラストラクチャを使用します
- 展開はエンドユーザーのデバイス上で複数の言語と既存のアーキテクチャをサポートする必要があります
- PC は、IT 管理コストとエンドユーザーに与える影響を最小限に抑えながら、安全で最新の状態に保ちます

## <a name="deployment-tools"></a>展開ツール

Contoso 社では自社の要件に基づいて、Configuration Manager (Current Branch) を使用した Windows 10 Enterprise と Microsoft 365 Apps for enterprise の展開を選択しました。Configuration Manager は大規模環境向けに拡張され、インストール、更新、設定に対する幅広い管理が可能です。また、Office の展開と管理をより簡単で効率的にするために、以下の機能も組み込まれています。

- ピア キャッシュ。遠隔地のデバイスに展開する際にネットワーク キャパシティが限られている場合に役立ちます
- Office クライアント管理ダッシュボード。Office の展開と更新の監視を容易にし、管理者が最新の展開と管理機能にアクセスできるようにします
- 高度な言語パックの展開。オペレーティング システムと同じ言語の自動展開を含みます
- 展開時にクライアントから既存のバージョンの Office を削除する方法を完全にサポートし、簡単に使用できるようにします

Configuration Manager のほかに、Contoso 社では[準備ツールキット](https://docs.microsoft.com/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro)も使用しました。これは、Office マクロとアドインとの互換性の問題を評価する Microsoft の無料ツールです。

## <a name="managing-the-deployment-and-updates"></a>展開および更新プログラムの管理

Microsoft 365 Apps for enterprise には、サービスとしての Office という新しいリリース モデルがあります。このサービス モデルにより、容易に新機能を最新のものにできますが、新リリースの展開やテストの方法に関する IT 部門のアプローチに対して、頻繁に変更が求められることになります。互換性の問題を最小限に抑え、コンピューターの最新状態を維持するため、Contoso 社では Windows と Office を次の 2 段階で展開しました。 

- 最初の段階では、組織全体にわたって、少数の代表的なデバイスに Microsoft 365 Apps for enterprise を展開しました。このパイロット グループは、Microsoft 365 Apps for enterprise でのアプリ、アドイン、およびハードウェアのテストに使用されました。
- 4 か月後、パイロット グループのアプリ、アドイン、ハードウェアに関する重要な問題を解決した後、Contoso 社では Microsoft 365 Apps for enterprise を組織内の残り (広範グループ) のデバイスに展開しました。 

Configuration Manager を使用して Office の更新を管理する代わりに、Contoso 社ではクラウドからの自動更新を有効にしました。クラウドベースの更新は、デバイスを最新の状態に保ちながら、管理上のオーバーヘッドを削減しました。 

Contoso 社では Office の展開に使用した 2 段階アプローチ、つまりパイロット グループ内のデバイスが組織の残り (広範グループ) のデバイスよりも 4 か月早く機能の更新を受け取る方法と同じアプローチを機能の更新にも使用しました。これを Office で可能にするために、Contoso 社では 2 つの推奨される[更新チャネル](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)を使用しました。 

- パイロット グループ用の半期チャネル (対象指定) 
- 広範グループ用の半期チャネル。 

半期チャネル (対象指定) は半期チャネルよりも 4 か月早いバージョンの Microsoft 365 Apps for enterprise をリリースするため、Contoso 社は更新プログラムを管理する必要なしに、それらを検証する時間があります。 

## <a name="deployment-process"></a>展開プロセス

Office の展開を完了するために、Contoso 社では Microsoft のベスト プラクティスの推奨事項を含む次のプロセスを実装しました。

1. 展開の前に準備ツールキットを使用して、アプリと Office アドインをテストし、Microsoft 365 Apps for enterprise との互換性を評価しました。
2. Configuration Manager では、Contoso 社はクライアント デバイス上でピア キャッシュを有効にしました。これは遠隔地にあるクライアントのデバイスに展開する際にネットワーク キャパシティが限られている場合に役立ちます。 
3. Configuration Manager で、パイロット グループと広範グループの 2 つの展開グループをデバイス コレクションとして定義しました。パイロットグループ (組織全体にわたる少数の代表的なデバイスを含む) は、Windows 10 Enterprise と Microsoft 365 Apps for enterprise を使用してアプリ、アドイン、およびハードウェアの追加テストを行うために使用されました。 
4. Office クライアント管理ダッシュボードと Office 365 インストーラー ウィザード (いずれも Configuration Manager コンソールの一部) を使用して、Office の展開パッケージを作成しました。2 つの Microsoft 365 Apps for enterprise パッケージを作成しました (1 つは半期チャネル (対象指定) のパイロット グループ用、1 つは半期チャネルの広範グループ用)。 
5. 各 Office パッケージの一部として、英語、フランス語、ドイツ語の言語パックが含まれていました。デバイスに、Office パッケージに含まれていない言語が必要な場合は、Office コンテンツ配信ネットワーク (CDN) から自動的にダウンロードされました。
6. Office パッケージの組み込み機能を使用して、Microsoft 365 Apps for enterprise のインストール前に既存の MSI バージョンの Office をすべて自動的に削除しました。
7. Configuration Manager では、Windows と Office パッケージをネットワーク上の配布ポイントに展開し、Configuration Manager の展開タスク シーケンスを実行して、パイロットの Microsoft 365 Apps for enterprise パッケージをパイロット グループに展開しました。
8. パイロット グループとの互換性問題を解決した後、Contoso 社ではタスク シーケンスを実行して、さまざまな Microsoft 365 Apps for enterprise パッケージを広範囲のグループに展開しました。

Contoso 社ではクラウドからデバイスを自動的に更新するよう選択しているため、Configuration Manger でプロセスを管理する必要はありませんでした。 デバイスは、最初の展開の一部として定義された更新チャネルに基づいて、直接クラウドから自動的に更新されます。 

次に Contoso 社の Microsoft 365 Apps for enterprise のインストール、および進行中の更新プログラムの展開アーキテクチャを示します。

![Contoso 社の Microsoft 365 Apps for enterprise の展開インフラストラクチャ](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>次の手順

Contoso 社が Microsoft 365 Enterprise で Microsoft Intune を使用して、組織全体で実行されるデバイスとアプリを管理する方法について[説明](contoso-mdm.md)します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise 用 Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md)

[展開ガイド](deploy-microsoft-365-enterprise.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
