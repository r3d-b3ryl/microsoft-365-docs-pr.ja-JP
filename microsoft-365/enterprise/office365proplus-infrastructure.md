---
title: 'フェーズ 4: Office 365 ProPlus'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise の Office 365 ProPlus インフラストラクチャを展開する手順。
ms.openlocfilehash: 3f6630d4c120609cbb1737ad96644d43eb2fda3c
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869531"
---
# <a name="phase-4-office-365-proplus"></a>フェーズ 4: Office 365 ProPlus

![](./media/deploy-foundation-infrastructure/O365proplus_icon.png)

*これは Microsoft 365 Enterprise および Microsoft 365 Education のバージョン E3 および E5 に適用されます。*

Microsoft 365 Enterprise に含まれている Office 365 ProPlus は、Office のサブスクリプション版です。Office 2016 と同様に、Office 365 ProPlus にはすべての Office アプリケーションが含まれており、これらのアプリケーションはクライアント デバイスに直接インストールされます。Office 2016 とは異なり、Office 365 ProPlus は定期的に更新され新機能が導入されます。また、ユーザーベースのライセンス モデルを採用しており、Office を最大 5 台のデバイスにインストールできます。詳細については、「[企業内での Office 365 ProPlus について](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)」を参照してください。

このフェーズでは、Microsoft 365 Enterprise の一部である Office 365 ProPlus をクライアント デバイスに展開します。このガイダンスの他に、展開の際に役立つ [Microsoft Fastrack](https://fasttrack.microsoft.com/office) を使用することをお勧めします。 

Office 365 ProPlus を使用すると、Microsoft 365 Enterprise の次の戦略的なビジネス シナリオが実現可能になります:

- リアルタイムまたは好きな時間にドキュメントで共同作業を行って、共同作成プロセスを簡略化します
- 集合知や専門知識を活用し、組織全体でファイル、情報、アイデアを発見、共有、発展させるよう人々を支援します
- ユーザーがビジネス プロセスを変換し、効率を向上できるよう支援します
- プロジェクト、タスク、期限を管理して、ビジネス目標を達成します
- デザイン、文書作成、コンテンツの探索などに関するインテリジェント アシスタンスを使用して、洗練された仕上がりにします
- 洞察を得、データを分析し、情報を共有することによって、皆が十分な情報を得たうえで決定を下せるようにします
- チーム内でコミュニケーションを図って、最新の情報に精通し、意見を求め、団結力と考えの一致を高めます
- 世界中のパートナー、同僚、顧客とのコミュニケーションを図り、あらゆるサイズのグループと計画的および臨時の通話やオンライン会議を実施します
- 組織内外でファイルを保管および共有して、組織の境界を越えてシームレスに作業を行います
- 柔軟なワーク スタイルを維持しながら、いつでもどこでもデバイスを使って多くのことを安全に成し遂げることができます
- 業界内で確証された世界標準のコンプライアンスに適合したコントロールと可視性により、安心感を提供します
- 情報を保護して、データ損失のリスクを軽減します
- デスクトップ ソフトウェアやデバイスで最新情報を入手し、セキュリティ上のリスクの軽減と IT 効率の最大化を図ります

詳細については、「[Microsoft 365 を使用したデジタル改革](http://transform.microsoft.com)」を参照してください。 

既に Office 365 ProPlus を展開している場合は、このフェーズの[終了条件](office365proplus-exit-criteria.md)を参照し、Microsoft 365 Enterprise の必須条件を満たしていることを確認してください。

>[!Note]
>Windows 10 Enterprise と Office 365 ProPlus の両方を展開し、[モダン デスクトップ](https://www.microsoft.com/microsoft-365/modern-desktop)に移行するには、「[モダン デスクトップ展開センター](http://aka.ms/howtoshift)」を参照してください。
>

## <a name="step-1-assess-your-environment"></a>手順 1: 環境を評価する

Office 365 ProPlus を展開する前に、「[Office 365 ProPlus を展開するため、実際の環境と要件を評価する](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus)」のガイダンスに従います。この評価では、システム要件、クライアント デバイスの詳細 (アーキテクチャや必要な言語など)、ライセンスの要件、ネットワーク容量、アプリケーションの互換性などを評価します。評価を実施すると、展開計画の一部としていくつかの重要な決定をする上で役立ちます。

## <a name="step-2-plan-your-deployment"></a>手順 2: 展開を計画する

実際の環境の評価が完了したら、「[Office 365 ProPlus の展開を計画する](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus)」のガイダンスに従って展開計画を策定します。この計画には次の内容が含まれます。 

- 使用するツール (System Center Configuration Manger や Office 展開ツール (OTD) など) を含め Office を展開する方法と Office のインストールを実行する場所
- Office の更新の管理方法
- 使用する更新チャネル (Office の更新チャネルにより、ユーザーが Office アプリケーションの機能更新を受け取る頻度が制御されます)
- 使用する Office インストール パッケージと展開グループ (どのユーザーにどの Office アプリケーションと言語をインストールするかなど)

「[計画資料](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus)」にはこれらのすべてのオプションのベスト プラクティスが収録されています (展開の管理、更新の管理、インストール パッケージの定義、展開グループの作成など)。 

## <a name="step-3-deploy"></a>手順 3: 展開する

手順 2 で策定した展開計画に基づき、展開方法を選択します。

- **[System Center Configuration Manager を使用して Office 365 ProPlus を展開する](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Configuration Manager を使用して展開を管理し、ネットワーク内の配布ポイントから Office をダウンロードして展開します。

- **[ODT を使用してクラウドから Office 365 ProPlus を展開する](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** ODT を使用して展開を管理し、Office CDN からクライアント デバイスに Office を直接インストールします。
 
- **[ODT を使用してローカル ソースから Office 365 ProPlus を展開する](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-a-local-source):** ODT を使用して展開を管理し、ネットワーク内のローカル ソースから Office をダウンロードして展開します。 

- **[Office ポータルから Office 365 ProPlus をセルフインストールする](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** Office ポータルから展開を管理し、ユーザーがポータルから各自のクライアント デバイスに Office インストールします。

多くの組織では、ユーザーに応じて前述のオプションを組み合わせて使用します。たとえば、ほとんどのユーザーに対しては Configuration Manager を使用して Office を展開しますが、社内ネットワークに頻繁に接続しない少数の作業員のグループにはセルフ インストールを有効にします。 

組織が Configuration Manager を使用する場合は、Current Branch にアップグレードし、最新リリースに更新することをお勧めします。詳細については、「[Configuration Manager のどのブランチを使用するか](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)」を参照してください。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft での Microsoft 365 Enterprise の活用方法

以下のリソースで、Microsoft の IT 担当者による Microsoft 365 Enterprise での Office 365 ProPlus の計画方法および展開方法を確認することができます。

- [Office 365 ProPlus 2016 をシームレスに展開するための組織の準備](https://www.microsoft.com/itshowcase/Office365adoption)
- [Microsoft Office 365 ProPlus の展開と更新](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [Microsoft Office 365 ProPlus の展開を支援するオートメーションと更新プログラム チャネル](https://www.microsoft.com/itshowcase/Article/Content/794/Automation-and-update-channels-help-deploy-Microsoft-Office-365-ProPlus) (ビデオ)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 社での Microsoft 365 Enterprise の活用方法

架空の代表的な多国籍企業である Contoso Corporation の [Office 365 ProPlus の展開](contoso-o365pp.md)方法をご覧ください。

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>次の手順

[Office 365 ProPlus インフラストラクチャの終了条件](office365proplus-exit-criteria.md)
