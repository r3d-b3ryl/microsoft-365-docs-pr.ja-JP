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
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社が Microsoft Endpoint Configuration Manager を使用して Microsoft 365 Apps for enterprise を展開する方法について説明します。
ms.openlocfilehash: 63993a27f23843fd2d75ef9bf08ae064ec46dc77
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637165"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>Contoso 社の Microsoft 365 Apps for enterprise の展開

Contoso 社は Pc を Windows 10 Enterprise にアップグレードし、エンタープライズ向け Microsoft 365 アプリを使用することで、より効果的なコラボレーション、セキュリティの向上、およびよりモダンなデスクトップ環境を実現しています。インフラストラクチャとビジネスのニーズを評価した後、Contoso は展開に関して次の主要な要件を特定しました。

- すべての Pc で、Microsoft 365 Apps for enterprise を実行する必要があります。
- 展開では、可能な場合は既存の管理ツールおよびインフラストラクチャを使用する必要があります。
- 展開では、ユーザーのデバイス上に複数の言語と既存のアーキテクチャがサポートされている必要があります。
- Pc は、最小限の IT 管理コストとユーザーへの影響を最小限に抑えて、最新の状態に保たれます。

## <a name="deployment-tools"></a>展開ツール

Contoso 社は、要件に基づいて、構成マネージャー (Current Branch) を使用して、Windows 10 Enterprise と Microsoft 365 Apps for enterprise を展開することを選択しました。構成マネージャーは大規模な環境に合わせて拡張され、インストール、更新、および設定を詳細に制御します。また、次のような Office をより簡単かつ効率的に展開および管理する機能が組み込まれています。

- ピアキャッシュ。これは、リモートの場所にあるデバイスに展開するときに、制限されたネットワーク容量で役立ちます。
- Office クライアント管理ダッシュボードを使用すると、Office の展開と更新の監視が容易になり、管理者は最新の展開および管理機能にアクセスできるようになります。
- インテリジェント言語パックの展開 (オペレーティングシステムと同じ言語の自動展開を含む)。
- 展開時にクライアントから既存のバージョンの Office を削除するための完全にサポートされた、使いやすい方法。

構成マネージャーに加えて、Contoso 社では [office アドインの準備ツールキットと VBA](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)を使用して、office マクロやアドインとの互換性の問題を評価しています。

## <a name="managing-deployment-and-updates"></a>展開と更新を管理する

Microsoft 365 enterprise 用アプリには、サービスとしての Office という新しいリリースモデルがあります。サービスモデルを使用すると、新機能に関する最新情報を簡単に入手できます。しかし、多くの場合、IT 部門が新しいリリースを展開してテストする方法を変更する必要があります。互換性の問題を最小限に抑え、コンピューターが最新の状態に保たれるようにするために、Contoso 社は Windows と Office を2段階で展開しています。

- 最初に、企業向けの Microsoft 365 アプリを組織全体の少数の代表的なデバイスに展開しました。 このパイロットグループは、Microsoft 365 Apps for enterprise を使用してアプリ、アドイン、およびハードウェアをテストするために使用されました。
- 4 か月後、パイロット グループのアプリ、アドイン、ハードウェアに関する重要な問題を解決した後、Contoso 社では Microsoft 365 Apps for enterprise を組織内の残り (広範グループ) のデバイスに展開しました。

構成マネージャーを使用して Office の更新プログラムを管理する代わりに、クラウドからの Contoso 社による自動更新を有効にします。 クラウドベースの更新プログラムは、デバイスを最新の状態に保つ一方で、管理上のオーバーヘッドを軽減します。

Contoso 社は、Office の展開に使用した機能更新プログラムに対して同じ2段階のアプローチを採用しています。パイロットグループ received 機能の更新プログラムは、組織の他の部分 (広範なグループ) のデバイスよりも4か月早く更新されています。 これを Office で可能にするために、Contoso 社では 2 つの推奨される[更新チャネル](https://docs.microsoft.com/DeployOffice/overview-update-channels)を使用しました。

- パイロット グループへの更新向け半期エンタープライズ チャネル (プレビュー)
- 広範なグループに対する更新に対してエンタープライズチャネルを Semi-Annual

エンタープライズ チャネル (プレビュー) は半期エンタープライズ チャネルよりも 4 か月早いバージョンの Microsoft 365 Apps for enterprise をリリースするため、Contoso 社は更新プログラムを管理する必要なしに、それらを検証する時間があります。

## <a name="deployment-process"></a>展開プロセス

Office の展開を完了するために、Contoso 社では Microsoft のベスト プラクティスの推奨事項を含む次のプロセスを実装しました。

1. 展開前に、Contoso 社は Office アドインと VBA の準備ツールキットを使用して、アプリと Office アドインをテストし、Microsoft 365 Apps for enterprise との互換性を評価していました。
1. 構成マネージャーでは、クライアントデバイスのピアキャッシュを有効にします。これにより、リモートの場所にクライアントデバイスに展開する際にネットワークの容量が制限されます。 
1. Contoso 社は、構成マネージャーでのデバイスコレクションとして、2つの展開グループを定義しています。パイロットグループと広範なグループ。 パイロットグループには、組織全体の代表的なデバイスのセットが含まれていました。アプリ、アドイン、およびハードウェアの追加テストには、Windows 10 Enterprise および Microsoft 365 Apps for enterprise が使用されていました。
1. Office クライアント管理ダッシュボードと office 365 インストーラウィザードを使用して、Office の展開パッケージを作成しました。これは、Configuration Manager コンソールの一部です。 エンタープライズパッケージ用に2つの Microsoft 365 アプリが構築されています。1つは Semi-Annual エンタープライズチャネル (プレビュー) のパイロットグループ用、もう1つは Semi-Annual エンタープライズチャネルの広範なグループ用です。
2. 各 Office パッケージには、英語、フランス語、ドイツ語の言語パックが含まれていました。 デバイスに Office パッケージに含まれていない言語が必要な場合、その言語パックは Office コンテンツ配信ネットワーク (CDN) から自動的にダウンロードされていました。
3. Office パッケージの組み込み機能を使用して、Microsoft 365 Apps for enterprise のインストール前に既存の MSI バージョンの Office をすべて自動的に削除しました。
4. 構成マネージャーでは、ネットワークを介して配布ポイントに Windows および Office パッケージを展開しました。 その後、構成マネージャーの展開タスクシーケンスを実行して、パイロットグループにエンタープライズパッケージのパイロット Microsoft 365 アプリを展開しました。
5. パイロットグループとの互換性の問題に対処した後、Contoso 社はタスクシーケンスを実行して、エンタープライズパッケージ用の Microsoft 365 アプリを広範なグループに展開しました。

Contoso 社ではクラウドからデバイスを自動的に更新するよう選択しているため、Configuration Manger でプロセスを管理する必要はありませんでした。 これらのデバイスは、最初の展開で定義された更新プログラムチャネルで、クラウドベースから直接更新されます。

ここでは、Contoso Microsoft 365 Apps for enterprise のインストールと継続的な更新プログラムの展開アーキテクチャについて説明します。

![Microsoft 365 Apps for enterprise の Contoso 展開インフラストラクチャ](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>次の手順

Contoso 社が microsoft 365 で microsoft Intune を使用して、自社のデバイスと、組織全体で実行されるアプリを管理する方法に[ついて説明](contoso-mdm.md)します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)

[Microsoft 365 for Enterprise の概要](microsoft-365-overview.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
