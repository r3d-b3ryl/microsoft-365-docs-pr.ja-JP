---
title: 'フェーズ 4: Microsoft 365 Apps for enterprise'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise の Microsoft 365 Apps for enterprises インフラストラクチャを展開する手順。
ms.openlocfilehash: 5143ef8872a7ebd119e77c6148288828a39e20d9
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011949"
---
# <a name="phase-4-microsoft-365-apps-for-enterprise"></a>フェーズ 4: Microsoft 365 Apps for enterprise

![フェーズ 4: Microsoft 365 Apps for enterprise](../media/deploy-foundation-infrastructure/O365proplus_icon.png)

*これは Microsoft 365 Enterprise および Microsoft 365 Education のバージョン E3 および E5 に適用されます。*

Microsoft 365 Enterprise には、Office のサブスクリプション版である Microsoft 365 Apps for enterprise が含まれています。 Office 2019 と同様に、Microsoft 365 Apps for enterprise にはすべての Office アプリケーションが含まれており、それらのアプリケーションはクライアント デバイスに直接インストールされます。 Office 2019とは異なり、Microsoft 365 Apps for enterprise は定期的に新機能が更新され、複数のデバイスに Office をインストールできるユーザーベースのライセンス モデルを採用しています。 詳細については、「[Microsoft 365 Apps for enterprise について](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps)」を参照してください。

このフェーズでは、Microsoft 365 Apps for enterprise の一部である Office 365 ProPlus をクライアント デバイスに展開します。このガイダンスの他に、展開の際に役立つ [Microsoft FastTrack](https://fasttrack.microsoft.com/office) を使用することをお勧めします。 

既に Microsoft 365 Apps for enterprise を展開している場合は、このフェーズの[終了条件](office365proplus-exit-criteria.md)を参照し、Microsoft 365 Enterprise の必須条件を満たしていることを確認してください。

>[!Note]
>Windows 10 Enterprise と Microsoft 365 Apps for enterprise の両方を展開するには、[デスクトップ展開センター](desktop-deployment-center-home.md)を参照してください。
>

## <a name="step-1-assess-your-environment"></a>手順 1: 環境を評価する

Microsoft 365 アプリを展開する前に、「[Microsoft 365 Apps for enterprise を展開するため、実際の環境と要件を評価する](https://docs.microsoft.com/DeployOffice/assess-microsoft-365-apps)」のガイダンスに従います。この評価では、システム要件、クライアント デバイスの詳細 (アーキテクチャや必要な言語など)、ライセンスの要件、ネットワーク容量、アプリケーションの互換性などを評価します。評価を実施すると、展開計画の一部としていくつかの重要な決定をする上で役立ちます。

## <a name="step-2-plan-your-deployment"></a>手順 2: 展開を計画する

実際の環境の評価が完了したら、「[Microsoft 365 アプリの展開を計画する](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps)」のガイダンスに従って展開計画を策定します。この計画には次の内容が含まれます。 

- 使用するツール (Microsoft Endpoint Configuration Manger や Office 展開ツールなど) を含め、Office を展開する方法と Office のインストールを実行する場所
- Office の更新の管理方法
- 使用する更新チャネル (Office の更新チャネルにより、ユーザーが Office アプリケーションの機能更新を受け取る頻度が制御されます)
- 使用する Office インストール パッケージと展開グループ (どのユーザーにどの Office アプリケーションと言語をインストールするかなど)

「[計画資料](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps)」にはこれらのすべてのオプションのベスト プラクティスが収録されています (展開の管理、更新の管理、インストール パッケージの定義、展開グループの作成など)。 

## <a name="step-3-deploy"></a>手順 3: 展開する

展開計画に基づき、展開方法を選択します。

- **[構成マネージャーを使用して、Microsoft 365 アプリを展開する](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-configuration-manager):** 構成マネージャーを使用して展開を管理し、ネットワーク内の配布ポイントから Office をダウンロードして展開します。

- **[ODT を使用してクラウドから Microsoft 365 アプリを展開する](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-cloud):** ODT を使用して展開を管理し、Office CDN からクライアント デバイスに Office を直接インストールします。
 
- **[Office ポータルから Microsoft 365 Apps for enterprise をセルフインストールする](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** Office ポータルから展開を管理し、ユーザーがポータルから各自のクライアント デバイスに Office インストールします。

多くの組織では、ユーザーに応じて前述のオプションを組み合わせて使用します。たとえば、ほとんどのユーザーに対しては Configuration Manager を使用して Office を展開しますが、社内ネットワークに頻繁に接続しない少数の作業員のグループにはセルフ インストールを有効にします。 

組織が Configuration Manager を使用する場合は、Current Branch にアップグレードし、最新リリースに更新することをお勧めします。詳細については、「[Configuration Manager のどのブランチを使用するか](https://docs.microsoft.com/mem/configmgr/core/understand/which-branch-should-i-use)」を参照してください。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft での Microsoft 365 Enterprise の活用方法

Microsoft のエキスパートが [Microsoft 365 Apps for enterprise の更新プログラムを展開および管理](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7)する方法について説明します。

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 社での Microsoft 365 Enterprise の活用方法

架空の代表的な多国籍企業である Contoso Corporation の [Microsoft 365 Apps for enterprise の展開](contoso-o365pp.md)方法をご覧ください。

![Contoso 社](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>次の手順

[Microsoft 365 Apps for enterprise インフラストラクチャの終了条件](office365proplus-exit-criteria.md)
