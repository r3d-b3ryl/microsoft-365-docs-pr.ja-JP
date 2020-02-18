---
title: 概要 - デスクトップの展開
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/20/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: デスクトップの展開プロセスの概要です。
ms.openlocfilehash: 62d18f23df55783c8b1f0c01f9f803a1d4bca0f0
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067498"
---
# <a name="getting-started---desktop-deployment"></a>概要 - デスクトップの展開

![](../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-2.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-1.png" alt="Getting Started" height="130" width="130" /></td>
<td><p><strong>はじめに: ユーザー、プロセス、およびテクノロジのガイダンス</strong></p>
<p>Windows 10 および Office 365 ProPlus の利点、大きな変更点、考慮事項を以前の展開と比べたうえで明確にし、Windows 10 および Office 365 ProPlus への移行をスムーズにできるようなベスト プラクティスを確立します。</p></td>
<td><a href="https://aka.ms/ddev0" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-13.png" alt="Getting Started" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>このシリーズでは、既存のツールを使用する最適な方法について説明し、クラウドによって実現される新しいテクノロジ、サービス、メソッドを紹介します。  デスクトップ展開プロセス全体を確認するには、[デスクトップ展開センター](https://aka.ms/HowToShift)を参照してください。
>

デスクトップ展開センターへようこそ。ここでは Windows 10 と Office 365 ProPlus への移行を計画および実現する際に役立つ情報をまとめて説明します。 最新の作業効率化、チームワーク、および共同作業のエクスペリエンスの機能を備えた、セキュリティで保護されたワークスペースを利用できます。

しばらく新しいデスクトップ環境を展開していなかった場合、幸いにも展開プロセスの多くが強化されています。 アプリケーションの互換性など過去の課題は現在ではそれほど問題になりません。 新しいツールに加えクラウドから提供される洞察を活用することで、これまでになく迅速かつ効率的に確実な移行を実現できます。

この序論では、変更点の概要と、デスクトップの展開プロセス全体のツアーを案内します。Windows 10 および Office 365 ProPlus への移行の推奨手順を示し、最新の管理テクノロジとアプローチを取り入れながら既存のツールとプロセスを活用する方法が詳述されています。

## <a name="why-upgrade"></a>アップグレードが必要な理由

Windows 10 と Microsoft のインテリジェンス クラウドを組み合わせることで、最も強力で安全なユーザー用のワークスペースを提供しやすくなると同時に、サポートのためのインフラストラクチャを簡素化することができます。

最新の管理方法における重要なテナントの 1 つとして、常に最新の状態にあるデバイスが挙げられます。 このシリーズでは、Windows 10 および Office 365 ProPlus への移行を支援するために用意されている新しい機能と、Windows 10 と Office 365 ProPlus 両方の半期のリリースを利用して、最新の状態を保つ方法について説明します。

[IT 担当者向けの Windows 10](https://www.microsoft.com/itpro/windows-10)

[エンタープライズでの Office 365 ProPlus について](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)

## <a name="what-has-changed"></a>変更点

まずは、前回のデスクトップの展開以降の変更点と改善点を見てみましょう。デスクトップ環境をしばらく変更していない場合は、Windows 7、Office 2010、または Office 2013 を使用している可能性があります。その場合、前回のメジャー アップグレード後に施されたいくつかの変更点に気付くはずです。以下が重要な変更点になります。

**ID とアクセス**: Windows 10 と Office 365 ProPlus は、クラウドの生産性、セキュリティ、および管理サービスへの接続性を備え、ID とアクセスの新しい管理サービスである Azure Active Directory (Azure AD) を基盤としています。 これにより、シングル サインオンが可能になり、クラウド サービス間の接続がセキュリティで保護されます。つまり、Azure AD は必須であり、これを活用することにより、Office 365、Intune、Windows Autopilot などの Microsoft 365 サービスの利点を生かすことができます。

[Microsoft 365](https://www.microsoft.com/microsoft-365/default.aspx)

**プリブート環境をセキュリティで保護**: BIOS の代わりに 64 ビットの UEFI ファームウェアが置き換えられます。 これは起動時間を短縮するだけでなく、Windows 10 に含まれる多くの最新のセキュリティ機能を有効にするために必要です。 Windows 10 は BIOS 上でも動作しますが、UEFI の使用を強くお勧めします。 BIOS から 64 ビットを利用する UEFI に切り替えていない場合は、今すぐ切り替えましょう。 Windows 10 のアップグレード中またはアップグレード後の切り替えを支援するツールが用意されています。

**クラウドベースのデバイス管理**: Microsoft Intune などのサービスは、他のモバイル デバイスと同様、Windows 10 デバイスを 1 か所から管理するのに役立ちます。 しかし、Microsoft Intune には、Microsoft Endpoint Configuration Manager で Windows 10 デバイスを共同管理するという独自の機能があります。 Configuration Manager を使用して Windows 10 に移行し、それから Microsoft Intune を追加することができます。 この連携を通じて、Microsoft Endpoint Configuration Manager は、Microsoft のインテリジェント クラウドに接続され、組織内のインテリジェント エッジになります。 管理者は、ユーザーのデバイスがどこにあっても安全に管理することができます。ユーザーが組織のインフラストラクチャに接続されているか、パブリック クラウドに接続されているかを問いません。

[Windows 10 デバイスの共同管理](https://docs.microsoft.com/configmgr/core/clients/manage/co-management-overview)

**クラウドベースの展開サービス**: 新しい PC を取得した際に、Microsoft 365 デバイスの導入に役立つ新しいクラウド サービスが導入されました。これは、Windows Autopilot 展開サービスと呼ばれます。 Autopilot はハードウェア プロバイダーと統合し、新しい PC は Autopilot に自動的に登録されます。このため、新しい PC をエンドユーザーに直接出荷することができます。 最初に PC の電源を入れると、組織の希望する設定にすばやく構成され、ユーザーの特定のニーズに合わせてカスタマイズされます。

[Windows Autopilot](https://www.microsoft.com/windowsforbusiness/windows-autopilot)

**クイック実行の展開**: Office デスクトップ アプリケーションをプロビジョニングする場合の推奨オプションは Office 365 ProPlus になります。 Office 365 ProPlus を利用すれば、開発中の Office の最新の技術革新の実践が可能となり、新しい機能を取得するまで何年も待つ必要はなくなります。 クイック実行と呼ばれるという新しいインストールも使用できます。

クイック実行は、過去の MSI ベースのパッケージとはまったく異なります。 クイック実行は今まで以上に速く軽く、バックグラウンドでの更新をサポートするため、ユーザーの起動および実行が維持されます。 それは引き続き Office のローカル コピーであり、Microsoft Endpoint Configuration Manager などの既存の展開ツールを使用した、アプリのプロビジョニングと構成も継続して行うことができます。

[Office 365 ProPlus の展開ガイド](https://docs.microsoft.com/DeployOffice/deployment-guide-for-office-365-proplus)

**半期の更新プログラム**: Windows 10 および Office 365 ProPlus に移行すると、新機能を備えた更新プログラムが半年ごとに配信されます。 Microsoft がクラウドから提供する洞察を活用すれば、これらの新機能の更新プログラムを数百または数千のデバイスにすばやく安心して展開することができます。 一括アップグレードと同様、機能更新プログラムは、以前のリリースからのアプリ、データ、設定を保持します。

## <a name="the-deployment-process-wheel"></a>展開プロセス全体

開始する前に、高レベルの計画と、その実現を支援するスポンサーを得ることが重要になります。 ここでは、Microsoft の展開プロセス全体における重要な手順の概要を説明しています。手順を参照すれば、以下の展開分野におけるコア チーム メンバーと管理するリソースを特定しやすくなります。

**[手順 1: デバイスとアプリの準備](https://aka.ms/mdd1)** 展開を成功させるには、まず自分が所有しているものを把握する必要があります。 つまり、デバイスやアプリのインベントリを作成し、互換性を確認することが重要になります。 クラウドベースのサービスである Desktop Analytics で利用できるツールを活用すると、インベントリの作成や互換性の確認がしやすくなります。 Desktop Analytics を使用すれば、何億台もの PC から収集された互換性のインテリジェンスと診断データを基に、デバイス上で実行されているアプリやドライバーを評価し、デスクトップ資産を整備することができます。 「展開可能な PC」の一覧を Desktop Analytics から Configuration Manager にエクスポートすることもできます。エクスポート後、対象となる PC のデータに基づくコレクションを作成できるようになります。

[アップグレードの準備を開始する](https://docs.microsoft.com/windows/deployment/upgrade/upgrade-readiness-get-started)

**[手順 2: ディレクトリとネットワークの準備](https://aka.ms/mdd2)** Azure Active Directory の実装がまだの場合は、まず実装してください。ID とアクセス管理を行う際に必要となります。 また、システム イメージ、アプリケーション パッケージ、ユーザー ファイル、更新プログラムが移動するネットワークの準備も必要です。 ネットワークには大量のデータが追加されます。そのため、組織の日常業務に支障がなく、この大量に読み込まれたデータを処理できるネットワークが必要になります。 Microsoft では、帯域幅の調整やピアツーピアのオプションから、動的帯域幅の清掃や差分更新まで、さまざまなネットワークの最適化を用意しています。

[BranchCache 対ピア キャッシュ](https://blogs.technet.microsoft.com/swisspfe/2018/01/25/branch-cache-vs-peer-cache/)

**[手順 3: Office と基幹業務アプリの配信](https://aka.ms/mdd3)** Windows は MSI ベースのインストールを引き続きサポートしていますが、自動インストールと継続的な更新プログラム用に最適化された新しいインストール方式もサポートしています。 Office 365 ProPlus および Office 2019 クライアントはクイック実行インストール テクノロジを使用します。 さまざまな UWP アプリケーションを利用可能になり、新しい MSIX ベースのパッケージ化されたアプリを基に、数多くのサード パーティのアプリや社内開発の基幹業務アプリを展開できるようになります。 ここでの手順を実行すると、アプリの自動展開の準備が整います。クイック実行、MSIX、従来の MSI ベースによるアプリの展開や、ビジネス向けの Microsoft Store で配布している UWP アプリの展開もできるようになります。

[MSIX とは](https://blogs.msdn.microsoft.com/sgern/2018/06/15/msix-intro/)

**[手順 4: ユーザー ファイルと設定の移行](https://aka.ms/mdd4)** ここは、PC の交換や更新サイクルにおける重要な手順です。ユーザーのファイル、データ、設定が正常に移行し、移行中に内容が保持されるようにする必要があります。 この手順では、よく知られているオプションや新しいオプションを含め、手動または自動で移行できるオプションを網羅します。

以前のアップグレードと同様、ユーザー状態移行ツールはこのプロセスを自動化する貴重なツールであり、Microsoft Endpoint Configuration Manager または Microsoft Deployment Toolkit による移行において重要な役割を果たします。 しかし、移行の際にすべてのデータを移動すると、PC ごとに数百 GB にも及ぶ転送が 2 回行われるため (1 回目は既存のデスクトップからの転送で、2 回目は新しいデスクトップへの転送)、PC 交換の時間的ボトルネックになる可能性があります。 OneDrive で有効になった新しいオプションである Known Folder Move を使用すれば、クラウド上の大きなサイズのユーザーのドキュメント、画像、デスクトップ ファイルを、展開前に同期することが可能となります。

[Windows の既知のフォルダーを OneDrive にリダイレクトして移動する](https://docs.microsoft.com/onedrive/redirect-known-folders)

**[手順 5: セキュリティとコンプライアンス](https://aka.ms/mdd5)**: セキュリティとコンプライアンスは、Windows 10 および Office 365 ProPlus に移行する際の非常に重要な分野です。新しく組み込まれた機能に精通し、既存の機能との相違点を把握しておくことが大切です。たとえば、仮想化ベースのセキュリティによる Windows 10 の新機能を利用すると、コア プロセスと機密事項がオペレーティング システムから独立するため、資格情報の盗難、ブラウザベースの悪用、悪質なコードの実行を防止することができます。さらに、Advanced Threat Protection のようなクラウド サービスには、セキュリティ強化、感染後の検出、調査、復旧対応を行う、統一されたプラットフォームが用意されています。また、Advanced Threat Protection は、悪意のある電子メールの添付ファイル、危険なハイパーリンクなどの脅威からもユーザーを守ります。

[Microsoft セキュリティ](https://www.microsoft.com/security/default.aspx)

**[Step 6: OS の展開と機能の更新プログラム](https://aka.ms/mdd6)**: 準備がすべて整ったら、次の手順は OS イメージを展開することです。複雑な作業の多くを、System Center Configuration Manager のタスク シーケンスとインフラストラクチャを使用して実行できます。推奨されるアプローチは、フェーズごとの展開です。代表的な一連のハードウェアとアプリケーションを使用して、最初に「早期採用グループ」を対象に設定し、展開を行います。その後、これらのデバイスやユーザーのデータを基に、展開の対象となる PC をさらに増やしていくことができます。

[Configuration Manager のオペレーティング システムの展開の概要](https://docs.microsoft.com/configmgr/osd/understand/introduction-to-operating-system-deployment)

**[手順 7: サービスとしての Windows および Office](https://aka.ms/mdd7)** これは、ユーザーのデスクトップ資産の維持方法に関する大きな変更を表しています。 Windows 10 および Office 365 ProPlus に移行すると、サービスとしての Windows および Office を管理することができます。 数年に一度の大規模なテクノロジの更新ではなく、新しい機能、エクスペリエンス、保護機能を継続してユーザーに提供します。 半期の機能更新プログラムは毎年秋と春に新しい機能を提供し、毎月の累積的な品質更新プログラムには、セキュリティ、信頼性、バグ修正プログラムが含まれます。 Office 2019 クライアントを展開することもできますが、Office 365 ProPlus に移行することを強くお勧めします。 これには Windows と同様のサービス プランが用意されており、ユーザーが Office アプリの更新プログラムを定期的に入手することもできます。

![](../media/getting-started-media/getting-started-media-2.png)

[サービスとしての Windows の概要](https://docs.microsoft.com/windows/deployment/update/waas-overview)
[サービスとしての Office の概要](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)

**[手順 8: ユーザーのコミュニケーションとトレーニング](https://aka.ms/mdd8)** この最後の手順は、チームワーク、コミュニケーション、セキュリティなどを強化するための新しい機能を使用するうえで非常に重要です。 早期に採用している組織に属さないユーザーを対象とした広範囲の展開を行う場合は、展開前にユーザーのコミュニケーションとトレーニングを実施することをお勧めします。 これを実施すれば、Office、Windows、他の基幹業務アプリやサービスの新機能に関して、ユーザーは自分に適した活用方法を見つけることができます。 また、Microsoft FastTrack のオンライン トレーニングによる支援も行っています。 さらに、コミュニケーション プランとタイムラインの無料サンプルを、電子メール、ソーシャルおよびイントラネットのテンプレートとともに公開しています。これらは Windows 10 の展開に役立ちます。 Microsoft 365 または Office 365 組織の場合は、直接サポートを受けることもできます。

## <a name="next-step"></a>次の手順

ここまで、Windows 10 と Office 365 ProPlus の新しい機能とこれまでとの相違点を確認し、推奨される展開プロセスの全体像を見てきました。 エンド ツー エンドのこのガイダンスを活用し、用意されているツールを駆使して、Windows 10 および Office 365 ProPlus への移行を始めましょう。

## <a name="step-1-device-and-app-readinesshttpsakamsmdd1"></a>[手順 1: デバイスとアプリの準備](https://aka.ms/mdd1)

