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
ms.openlocfilehash: 4a36e33a6f2ef6df880864dd852f0f63056946e6
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679040"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>Contoso 社の Microsoft 365 Apps for enterprise の展開

Contoso upgraded their PCs to Windows 10 Enterprise and Microsoft 365 Apps for enterprise to enable more effective collaboration, better security, and a more modern desktop experience. After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:

- すべての PC が Microsoft 365 Apps for enterprise を実行する必要があります
- 可能な場合は、既存の管理ツールとインフラストラクチャを使用します
- 展開はエンドユーザーのデバイス上で複数の言語と既存のアーキテクチャをサポートする必要があります
- PC は、IT 管理コストとエンドユーザーに与える影響を最小限に抑えながら、安全で最新の状態に保ちます

## <a name="deployment-tools"></a>展開ツール

Based on their requirements, Contoso chose to deploy Windows 10 Enterprise and Microsoft 365 Apps for enterprise with Configuration Manager (Current Branch). Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Office, including:

- ピア キャッシュ。遠隔地のデバイスに展開する際にネットワーク キャパシティが限られている場合に役立ちます
- Office クライアント管理ダッシュボード。Office の展開と更新の監視を容易にし、管理者が最新の展開と管理機能にアクセスできるようにします
- 高度な言語パックの展開。オペレーティング システムと同じ言語の自動展開を含みます
- 展開時にクライアントから既存のバージョンの Office を削除する方法を完全にサポートし、簡単に使用できるようにします

Configuration Manager のほかに、Contoso 社では[準備ツールキット](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)も使用しました。これは、Office マクロとアドインとの互換性の問題を評価する Microsoft の無料ツールです。

## <a name="managing-the-deployment-and-updates"></a>展開および更新プログラムの管理

Microsoft 365 Apps for enterprise has a new release model: Office as a service. The service model makes it easy to stay up to date with new features, but often requires a change in approach for IT departments in how new releases are deployed and tested. To minimize any compatibility issues and to ensure their computers stayed up to date, Contoso deployed Windows and Office in two stages: 

- For the first stage, they deployed Microsoft 365 Apps for enterprise to a small set of representative devices across the organization. This pilot group was used to test apps, add-ins, and hardware with Microsoft 365 Apps for enterprise
- 4 か月後、パイロット グループのアプリ、アドイン、ハードウェアに関する重要な問題を解決した後、Contoso 社では Microsoft 365 Apps for enterprise を組織内の残り (広範グループ) のデバイスに展開しました。 

Instead of managing updates to Office with Configuration Manager, Contoso enabled automatic updates from the cloud. Cloud-based updates reduced their administrative overhead while ensuring the devices stayed up to date. 

Contoso followed the same two-stage approach for feature updates that they used for deploying Office: devices in the pilot group received feature updates four months earlier than devices in the rest of the organization (the broad group). To enable this for Office, Contoso used two recommended [update channels](https://docs.microsoft.com/DeployOffice/overview-update-channels): 

- パイロット グループへの更新向け半期エンタープライズ チャネル (プレビュー) 
- 広範グループ用の半期エンタープライズ チャネル。 

エンタープライズ チャネル (プレビュー) は半期エンタープライズ チャネルよりも 4 か月早いバージョンの Microsoft 365 Apps for enterprise をリリースするため、Contoso 社は更新プログラムを管理する必要なしに、それらを検証する時間があります。 

## <a name="deployment-process"></a>展開プロセス

Office の展開を完了するために、Contoso 社では Microsoft のベスト プラクティスの推奨事項を含む次のプロセスを実装しました。

1. 展開の前に準備ツールキットを使用して、アプリと Office アドインをテストし、Microsoft 365 Apps for enterprise との互換性を評価しました。
2. Configuration Manager では、Contoso 社はクライアント デバイス上でピア キャッシュを有効にしました。これは遠隔地にあるクライアントのデバイスに展開する際にネットワーク キャパシティが限られている場合に役立ちます。 
3. They defined two deployment groups as device collections in Configuration Manager: a pilot group and a broad group. The pilot group, which included a small set of representative devices across the organization, was used to do additional testing of apps, add-ins, and hardware with Windows 10 Enterprise and Microsoft 365 Apps for enterprise. 
4. They created deployment packages for Office using the Office Client Management dashboard and the Office 365 Installer wizard, both of which are part of the Configuration Manager console. They built two Microsoft 365 Apps for enterprise packages, one for the pilot group on the Semi-Annual Enterprise Channel (Preview) and one for the broad group on the Semi-Annual Enterprise Channel. 
5. As part of each Office package, they included English, French, and German Language packs. If a device required a language not included in the Office package, it was automatically downloaded from the Office Content Delivery Network (CDN).
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
