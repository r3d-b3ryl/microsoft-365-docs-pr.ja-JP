---
title: Contoso 社の Microsoft 365 Apps for enterprise の展開
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: scotv
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社が Microsoft Endpoint Configuration Manager を使用して Microsoft 365 Apps for enterprise を展開する方法について説明します。
ms.openlocfilehash: 8b6fb639083145c728870156d848b75897483d25
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65096548"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>Contoso 社の Microsoft 365 Apps for enterprise の展開

Contoso は PC をWindows 10 EnterpriseとMicrosoft 365 Apps for enterpriseにアップグレードし、より効果的なコラボレーション、セキュリティの向上、およびよりモダンなデスクトップ エクスペリエンスを実現しました。 インフラストラクチャとビジネス のニーズを評価した後、Contoso はデプロイに関する次の主要な要件を特定しました。

- すべての PC はMicrosoft 365 Apps for enterprise実行する必要があります。
- デプロイでは、可能な限り既存の管理ツールとインフラストラクチャを使用する必要があります。
- 展開では、ユーザーのデバイスで複数の言語と既存のアーキテクチャをサポートする必要があります。
- PC は最新の状態を保ち、IT 管理コストを最小限に抑え、ユーザーへの影響を最小限に抑えてセキュリティで保護する必要があります。

## <a name="deployment-tools"></a>展開ツール

Contoso は、要件に基づいて、Configuration Manager (Current Branch) を通じてWindows 10 EnterpriseとMicrosoft 365 Apps for enterpriseをデプロイすることを選択しました。 Configuration Manager は、大規模な環境向けに調整されていて、インストール、更新、設定についての詳細な制御を実現します。 さらに、次に示す組み込みの機能により、Office の展開および管理が簡単で効率的になります。

- ピア キャッシュ。リモートの場所のデバイスに展開するときに、ネットワーク容量の制限に役立ちます。
- Officeクライアント管理ダッシュボードを使用すると、更新プログラムを簡単に展開したり、更新プログラムを監視したりOffice展開したり、管理者が最新の展開機能や管理機能にアクセスしたりできます。
- オペレーティング システムと同じ言語を自動的にデプロイするなど、インテリジェントな言語パックの展開。
- 展開中にクライアントから既存のバージョンのOfficeを削除する完全にサポートされ、使いやすい方法です。

Contoso は、Configuration Managerに加えて、Microsoft の無料ツール[である Office アドインと VBA の準備](/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)Toolkitを使用して、Office マクロとアドインとの互換性の問題を評価しました。

## <a name="managing-deployment-and-updates"></a>デプロイと更新プログラムの管理

Microsoft 365 Apps for enterpriseには、サービスとしてOfficeという新しいリリース モデルがあります。 サービス モデルを使用すると、新機能を簡単に最新の状態に保つことができます。 ただし、多くの場合、IT 部門は新しいリリースのデプロイ方法とテスト方法を変更する必要があります。 互換性の問題を最小限に抑え、コンピューターを最新の状態に保つために、Contoso は次の 2 つの段階でWindowsとOfficeを展開しました。

- まず、組織全体の代表的なデバイスの小さなセットにMicrosoft 365 Apps for enterpriseを展開しました。 このパイロット グループは、Microsoft 365 Apps for enterpriseを使用してアプリ、アドイン、ハードウェアをテストするために使用されました。
- 4 か月後、パイロット グループのアプリ、アドイン、ハードウェアに関する重要な問題を解決した後、Contoso 社では Microsoft 365 Apps for enterprise を組織内の残り (広範グループ) のデバイスに展開しました。

Contoso は、Configuration Managerを使用してOfficeの更新プログラムを管理する代わりに、クラウドからの自動更新を有効にしました。 クラウドベースの更新により、管理のオーバーヘッドが軽減され、デバイスが最新の状態を維持できるようになります。

Contoso は、Officeの展開に使用したものと同じ 2 段階の機能更新プログラムのアプローチに従いました。パイロット グループのデバイスは、組織の残りのデバイス (広範なグループ) よりも 4 か月前に機能更新プログラムを受け取っています。 これを Office で可能にするために、Contoso 社では 2 つの推奨される[更新チャネル](/DeployOffice/overview-update-channels)を使用しました。

- パイロット グループへの更新向け半期エンタープライズ チャネル (プレビュー)
- Semi-Annual Enterprise チャネルで広範なグループの更新を行う

エンタープライズ チャネル (プレビュー) は半期エンタープライズ チャネルよりも 4 か月早いバージョンの Microsoft 365 Apps for enterprise をリリースするため、Contoso 社は更新プログラムを管理する必要なしに、それらを検証する時間があります。

## <a name="deployment-process"></a>展開プロセス

Office の展開を完了するために、Contoso 社では Microsoft のベスト プラクティスの推奨事項を含む次のプロセスを実装しました。

1. Contoso はデプロイ前に、Office アドインと VBA の準備Toolkitを使用して、アプリとOffice アドインをテストし、Microsoft 365 Apps for enterpriseとの互換性を評価しました。
1. Configuration Managerでは、クライアント デバイスでピア キャッシュを有効にしました。これにより、リモートの場所のクライアント デバイスに展開するときにネットワーク容量が制限されます。 
1. Contoso は、Configuration Managerのデバイス コレクションとして 2 つの展開グループ (パイロット グループと広範なグループ) を定義しました。 組織全体の代表的なデバイスの小さなセットを含むパイロット グループは、Windows 10 EnterpriseとMicrosoft 365 Apps for enterpriseを使用したアプリ、アドイン、ハードウェアの追加テストに使用されました。
1. Office クライアント管理ダッシュボードと Office 365 インストーラー ウィザードを使用して、Officeの展開パッケージを作成しました。どちらもConfiguration Manager コンソールの一部です。 Semi-Annual Enterprise チャネル (プレビュー) のパイロット グループ用と、Semi-Annual Enterprise チャネルの広範なグループ用の 2 つのMicrosoft 365 Apps for enterprise パッケージを構築しました。
2. 各Officeパッケージには、英語、フランス語、ドイツ語の言語パックが含まれていました。 デバイスでOffice パッケージに含まれていない言語が必要な場合、その言語パックはOffice Content Delivery Networkから自動的にダウンロードされました (CDN)。
3. Office パッケージの組み込み機能を使用して、Microsoft 365 Apps for enterprise のインストール前に既存の MSI バージョンの Office をすべて自動的に削除しました。
4. Configuration Managerでは、Windows パッケージとOffice パッケージをネットワーク全体の配布ポイントにデプロイしました。 次に、Configuration Manager展開タスク シーケンスを実行して、パイロット Microsoft 365 Apps for enterprise パッケージをパイロット グループに展開しました。
5. パイロット グループとの互換性の問題に対処した後、Contoso はタスク シーケンスを実行して、Microsoft 365 Apps for enterprise パッケージを広範なグループに展開しました。

Contoso 社ではクラウドからデバイスを自動的に更新するよう選択しているため、Configuration Manger でプロセスを管理する必要はありませんでした。 デバイスは、初期デプロイで定義された更新チャネルに基づいて、クラウドから直接自動的に更新されます。

Contoso Microsoft 365 Apps for enterpriseのインストールと継続的な更新プログラムの展開アーキテクチャを次に示します。

![Microsoft 365 Apps for enterprise用の Contoso デプロイ インフラストラクチャ。](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>次の手順

Contoso がエンタープライズ向けの[Microsoft 365でMicrosoft Intuneを使用](contoso-mdm.md)して、組織全体で実行されるデバイスとアプリを管理する方法について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Apps for enterprise](/deployoffice/deployment-guide-microsoft-365-apps)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)