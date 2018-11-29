---
title: 手順 3 - Office および LOB アプリの配信
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Office および LOB アプリの配信方法について説明します。
ms.openlocfilehash: 2bae1f159f7c8ae947d4afddfe1e608cdd8bc85b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869653"
---
# <a name="step-3-office-and-lob-app-delivery"></a>手順 3: Office および LOB アプリの配信

この時点で、Office および基幹業務アプリを配信する準備は整っています。そのための方法はいくつかありますが、その中には優れた新しいオプションが含まれています。現在のニーズに対応する最適な方法を調べて選択するために、ある程度の時間を割いてください。

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-6.png" alt="Step 3" height="130" width="130" /></td>
<td><p><strong>手順 3: Office および LOB アプリの配信</strong></p>
<p>目的のアプリがパッケージ化されていて、自動インストールの準備が整っていることを確認してください。Office 365 ProPlus のクイック実行パッケージが、Office アプリケーションの構成、配信および最新状態の維持のための新しいオプションをどのように提供するかについて説明します。</p></td>
<td><a href="https://aka.ms/ddev3" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-16.png" alt="Step 3" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>Office および LOB アプリの配信は、推奨される展開プロセスの輪における 3 番目の手順であり、Office と LOB をインストールおよび管理するためのオプションをカバーしています。展開が正常に成功するように、最初の 2 つの手順は省略しないでください。完全なデスクトップ展開プロセスを確認するには、「[モダン デスクトップ展開センター](https://aka.ms/HowToShift)」を参照してください。
>

一部のアプリケーションは 32 ビットまたは 64 ビットのどちらかでコンパイルされたバージョンとしてのみ使用できますが、それ以外の Office 365 ProPlus などのアプリケーションは 32 ビットおよび 64 ビットの両方でネイティブにコンパイルされたコードとして使用できるため、どちらのバージョンを展開するかが重大な決断の 1 つになります。新しいデバイスに備わった追加の計算能力と RAM を活用するには、64 ビット バージョンの使用が望まれますが、その前に、アドインやファイルに関連する互換性の問題を把握しておく必要があります。そのために、まず、「手順 1: デバイスとアプリの準備」を再確認しておく必要があります。

障害になるものがない場合は、Microsoft Office を含めてすべてのアプリの 64 ビット バージョンを展開することをお勧めします。64 ビット ネイティブでコンパイルされたアプリは、最高のパフォーマンスを発揮する、最も将来性のある選択になります。

Windows にアプリをインストールするための方法とモデルは多数あります。次に、選択可能な配信のオプションについて説明します。

[Windows 10 アプリケーションの管理](https://docs.microsoft.com/ja-JP/windows/application-management/)

## <a name="msi-based-deployments"></a>MSI ベースの展開

基幹業務アプリについては、MSI ベースのパッケージまたは実行可能ファイルを使用して、OS 展開のタスク シーケンスの一部としてアプリをインストールすることになるでしょう。そうしたパッケージは、Windows 10 でも引き続き動作します。

System Center Configuration Manager や Microsoft Intune などのソフトウェア展開ツールも、MSI パッケージ型のアプリを配信するように最適化されています。Windows 10 でアプリを検証していれば、アプリの配信に System Center Configuration Manager (現在のブランチ) を使用できます。Microsoft Intune の「ポータル サイト」を使用している場合は、IT 部門によって承認された組織が利用できるアプリの選択を拡張して、最新のアプリケーションを含めるようにすると、ユーザーは必要なものを自分で選択できます。

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-3.png)

## <a name="pc-imaging"></a>PC のイメージング

もう 1 つの一般的なアプリ配信の方法は、PC のイメージングです。この場合は、タスク シーケンスまたは手動のどちらかでサンプル PC にアプリケーションをインストールしてから、必要なアプリケーションがプレインストールされた状態のシステム イメージをキャプチャします。イメージングによるビルドとキャプチャのアプローチは、新しい PC のプロビジョニングにかかる時間を短縮できますが、そのイメージに含まれるオペレーティング システムとアプリは、すぐに古いものになってしまう点に注意してください。Windows 10 および Office 365 ProPlus の「累積的な更新プログラム」モデルは、この問題への対応に役立ちますが、問題を完全に排除することにはなりません。そのため、展開時にイメージの外部からアプリケーションをインストールする、シン イメージのアプローチをお勧めします。

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-4.png)

イメージに Office 365 ProPlus を含める必要がある場合は、ユーザー ベースのライセンス認証を使用することになる点に注意してください。システム管理者が事前にライセンス認証することはできません。「Office 展開ツール」を使用して、イメージングするデバイスに Office をプレインストールして、ユーザー サインインをスキップします。ユーザーはサインインして、ライセンス認証の割り当てなどの初回使用時のサインインを利用する機能を活用できます。

[オペレーティング システムをインストールするタスク シーケンスの作成](https://docs.microsoft.com/ja-JP/sccm/osd/deploy-use/create-a-task-sequence-to-install-an-operating-system)

## <a name="click-to-run"></a>クイック実行 

Office 365 ProPlus は、クイック実行を使用してインストールされます。クイック実行は、近日リリースされる Windows 用 Office 2019 リリースのすべてのバージョンで MSI ベースのパッケージ化に置き換わるものです。これには、インストールの高速化、更新の高速化と能率化、アンインストールのクリーン化などの多数の利点があります。

クイック実行によって配信されたプログラムは、コンピューター上の仮想アプリケーション環境内で実行されるため、別のアプリケーションと競合することなく共存できます。また、占有されるディスク領域は MSI ベースのパッケージの半分程度で済みます。さらに、クイック実行はプログラムのストリーミングをサポートしているため、最も一般的に使用される機能を最初にストリーミングすることで、ユーザーは、最初に Office が完全にインストールされるまで待機するのではなく、数分間で Office アプリケーションの使用を開始できます。これは、初期展開の場合以外にも重要なことです。更新プログラムは、ユーザーに影響を与えることなくバックグラウンドでシームレスにストリーミングされるからです。

System Center Configuration Manager は、引き続き Office 365 ProPlus の広範囲の展開に使用できます。System Center Configuration Manager (現在のブランチ) には、最新版 Office カスタマイズ ツールのネイティブ サポート、インストール時のクイック実行に対応するパッケージのカスタマイズ、およびインストール後のソフトウェア更新管理のネイティブ サポートがあります。

[Office 365 ProPlus の展開ガイド](https://docs.microsoft.com/ja-JP/deployoffice/deployment-guide-for-office-365-proplus)

[Office 365 ProPlus にアップグレードする際に Office の既存の MSI バージョンを削除する](https://docs.microsoft.com/ja-JP/deployoffice/upgrade-from-msi-version)

[Configuration Manager を使用した Office 365 ProPlus の管理](https://docs.microsoft.com/ja-JP/sccm/sum/deploy-use/manage-office-365-proplus-updates)

[Microsoft Intune で Windows 10 デバイスに Office 365 アプリを割り当てる](https://docs.microsoft.com/ja-JP/intune/apps-add-office365)

## <a name="browser-based-apps"></a>ブラウザー ベースのアプリ

ブラウザー ベースのアプリケーションが引き続き期待どおりに動作するようにするには、いくつかの考慮すべき事項があります。Microsoft Edge との互換性に問題がある特定の Web サイトとアプリがある場合は、エンタープライズ モード サイト一覧を使用することで、その Web サイトが自動的に Internet Explorer 11 で開かれるようになります。

さらに、イントラネット サイトが Microsoft Edge では正常に動作しなくなることがわかっている場合は、すべてのイントラネット サイトが自動的に Internet Explorer 11 で開かれるように設定することもできます。このプロセスでは、それぞれのサイトに IE11 を使用するかどうかを制御するために XML ファイルを使用します (設定の適用にはグループ ポリシーを使用します)。

ここまでは、よく知られている展開方法について説明しました。それ以外にも、検討対象になる 2 つの新しいアプリ展開のアプローチがあります。

[エンタープライズ モードとは](https://docs.microsoft.com/ja-JP/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#what-is-enterprise-mode)

## <a name="microsoft-store-for-business"></a>ビジネス向け Microsoft Store 

ビジネス向け Microsoft Store は、Windows 10 デバイスの無料/有料アプリを大規模に検索、取得、管理および配布する柔軟な方法を提供します。IT 管理者は、自分のプライベート ストアに選択した Microsoft Store アプリと独自のカスタム アプリを公開できます。また、必要に応じてライセンスの割り当てと再使用ができます。ユーザーは、このストアにのみ転送されるため、承認されたアプリケーションのみを見つけてインストールできます。

Store アプリは、UWP アプリとしてネイティブにビルドすることも、デスクトップ ブリッジを使用して Store の既存のアプリを再パッケージ化して、Windows 10 の最新のエクスペリエンスを追加することもできます。Windows 10 のエクスペリエンスを際立たせるために使用するコードを除いて、アプリは未変更のまま引き続き完全信頼のユーザー モードで実行されます。

## <a name="msix-containerization"></a>MSIX コンテナー化

アプリケーション パッケージの新しいオプションが MSIX です。MSIX は Windows で使用可能なコンテナー化テクノロジを使用して、クイック実行、UWP および MSI パッケージの最良の側面をまとめて提供します。既存のインストーラー (EXE、MSI、APPV、APPX など) を直接 MSIX に移行するツールを使用することで、MSIX コンテナー化が、現在使用されている多数のインストール テクノロジに統合されたパスを提供することがわかります。MSIX のサポートは、Windows の現行バージョンに含まれています。Windows 10 RS5 を実行するデバイスには、MSIX パッケージ型のアプリをインストールして実行するために必要なものがすべて含まれています。Windows 10 は、受け入れた MSIX コンテナーを動的に統合しますが、アプリケーションはオペレーティング システムから分離された状態を維持します。

コンテナー化によって、パッケージのアンインストールと削除がクリーンなものになります。これは、システムにアイテムを残してしまうことがある、現在の多くの MSI および EXE ベースのパッケージとは異なります。また、アプリケーションのインストールには標準ユーザーの資格情報のみが必要になります。MSIX コンテナーのインストールには管理者の資格情報は必要ありません。MSIX コンテナーによって、更新も効率的になります。更新プログラムが公開されたときに、ブロック レベルの差分を使用することで、正味の新しいバイナリのみが適用されます。これにより、更新プログラムのペイロードが小さくなり、ネットワーク帯域幅の使用量が減って展開が高速化されます。

MSIX の詳細については、「[MSIX 技術コミュニティ サイト](https://techcommunity.microsoft.com/t5/MSIX/ct-p/MSIX)」を参照してください。

## <a name="next-step"></a>次の手順

## <a name="step-4-user-files-and-settingshttpsakamsmdd4"></a>[手順 4: ユーザーのファイルと設定](https://aka.ms/mdd4)

## <a name="previous-step"></a>前の手順

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[手順 2: ディレクトリとネットワークの準備](https://aka.ms/mdd2) 