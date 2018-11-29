---
title: 手順 1 - デバイスとアプリの準備
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
description: 環境内のデバイスとアプリの準備を評価する方法について説明します。
ms.openlocfilehash: a9fa85ea37de06399aa2264b09c61e588edc2107
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869647"
---
# <a name="step-1-device-and-app-readiness"></a>手順 1: デバイスとアプリの準備

デバイスとアプリのインベントリを使用してデスクトップ展開プロジェクトを開始し、転送するものに優先度を設定し、優先度が設定されたアプリとデバイスをテストし、展開の準備に必要なものを修復します。

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Step 1" height="130" width="130" /></td>
<td><p><strong>手順 1: デバイスとアプリの準備</strong></p>
<p>デバイスとアプリのインベントリを使用してデスクトップ展開プロジェクトを開始し、転送するものに優先度を設定し、優先度が設定されたアプリとデバイスをテストし、展開の準備に必要なものを修復します。</p></td>
<td><a href="https://aka.ms/ddev1" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-14.png" alt="Step 1" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>デバイスとアプリの準備は、推奨されている展開プロセスの輪における最初の手順であり、アプリケーションとハードウェアの互換性に関する包括的な側面をカバーします。完全なデスクトップ展開プロセスを確認するには、「[モダン デスクトップ展開センター](https://aka.ms/HowToShift)」を参照してください。
>

これまで、ユーザーのデスクトップをアップグレードする際には、アプリケーションとハードウェアの互換性が大きなハードルになっていました。Windows 10 および Office 365 ProPlus への移行を計画しているときには、好都合なことに、過去 10 年間に作成されたアプリケーションのほとんどが Windows 10 で稼働するものであり、組織が Office 2010 以降の各バージョンで使用している COM アドインと VBA マクロは最新バージョンの Office でも変更なしで動作します。

そのため、組織の規模と歴史によっては、アプリケーションとハードウェアの互換性を検証することが、推奨される 8 フェーズの展開プロセスにおける重要な最初の手順になることがあります。

この記事では、最初のフェーズであるデバイスとアプリの準備に、新しい Windows Analytics の Upgrade Readiness ツールを使用する方法について説明します。このツールは、インテリジェントなクラウド ベースのソリューションであり、Windows ライセンスで使用できます。

現時点で目的の環境に Windows Analytics をセットアップしていない場合や、試用のためにサインアップしようとしている場合は、[Windows Analytics ページ](http://www.aka.ms/windowsanalytics)に移動して開始してください。

## <a name="recommended-tool-windows-analytics-upgrade-readiness"></a>推奨されるツール: Windows Analytics の Upgrade Readiness

Windows Analytics の Upgrade Readiness は、従来のデスクトップ管理システムよりも多くのメリットをもたらす推奨ツールです。これは、エージェントレス型のツールであり、実行する必要のある手順をガイドします。数百万台のコンシューマー PC のアップグレードを通じて収集したアプリケーションとドライバーの互換性情報を活用して、詳細な評価を示し、アップグレードの障害になる可能性のある互換性の問題を特定すると共に、Microsoft にとって既知の提案される修正プログラムへのリンクが示されます。

Window Analytics の Upgrade Readiness をセットアップするには、まず、Azure サブスクリプションを設定して、そのサブスクリプションに Azure Log Analytics ワークスペースを含めておく必要があります。Windows Analytics Upgrade Readiness サービスを実行すると、インターネットに接続された Windows 7 SP1 以降のデバイスを「グループ ポリシー」設定から登録できるようになります。これは簡単なことです。展開するエージェントはありません。また、Windows Analytics Upgrade Readiness のビジュアル ワークフローにより、パイロット展開から運用展開へのガイドが示されます。必要に応じて、Windows Analytics Upgrade Readiness から System Center Configuration Manager などのソフトウェア展開ツールにデータをエクスポートして、展開の準備が整ったときに PC を直接対象としてコレクションを作成できます。

## <a name="device-and-app-readiness-process"></a>デバイスとアプリの準備プロセス

デバイスとアプリの準備は、「1. インベントリ」、「2. 優先度設定」、「3. テスト」、「4. 修復」の 4 つの手順で成立します。これらの手順について、順番に説明します。

### <a name="1-inventory"></a>1\. インベントリ

Windows Analytics Upgrade Readiness サービスは、エージェントレス型のプロセスを使用して、デスクトップ資産全体にわたるコンピューター、アプリケーション、および Office アドインをインベントリに登録します。

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-3.png)

さらに、頻繁にアクセスされるインターネット サイト、アプリおよびイントラネットの場所に関するレポートを示します。これは、この後の互換性テストの役に立ちます。

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-4.png)

### <a name="2-prioritize"></a>2\. 優先度設定

インベントリの作成により、Windows Analytics Upgrade Readiness は、優先度を設定する際に役立つ、組織で最も一般的に使用されているアプリとハードウェアを特定します。また、できるだけ多くの PC の展開のために排除する障害に注目する際にも役立ちます。

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-5.png)

さらに、次の手順「テスト」で問題を解決するために必要な更新プログラムを評価する際に役立つガイダンスも提供します。

### <a name="3-testing"></a>3\. テスト

インベントリに登録されたほとんどのアプリケーション、ドライバー、およびアドインは、そのままの状態で動作することがわかるでしょう。Windows Analytics Upgrade Readiness によって問題があると評価されたアイテムについては、互換性問題を解決するためのバージョン更新プログラムがある場所が含まれた既知の情報が示されます。重要でなく展開されている数が少ないアプリケーションと古いデバイスに時間とリソースを費やすのではなく、そうしたアイテムはユーザーと協力して使用中止にして置き換えるようにします。

Windows Analytics の Upgrade Readiness を使用して、ユーザーがアクセスした Web サイトと Web アプリのうち Microsoft Edge ブラウザーでサポートされなくなったレガシ テクノロジ (ActiveX コントロール、ブラウザー ヘルパー オブジェクト、VBScript など) を依然として使用しているものを識別することで、ブラウザー ベースの互換性問題についても評価できます。ユーザーは、そうしたサイトに対して引き続き Internet Explorer 11 を使用する必要があるため、これに該当するサイトは Enterprise Mode Site List Manager を使用して[エンタープライズ モード サイト一覧](https://docs.microsoft.com/ja-JP/microsoft-edge/deploy/emie-to-improve-compatibility)に追加してください。

さらに、Office 365 ProPlus への移行を円滑に進めるために、[Readiness Toolkit for Office](https://docs.microsoft.com/ja-JP/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) を利用して、アドインと Microsoft Visual Basic for Applications (VBA) マクロの互換性をテストすることもできます。

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-6.png)

### <a name="4-remediation"></a>4\. 修復

デバイスとアプリの準備の最終フェーズでは「修復」を実行します。このフェーズでは、必要なソフトウェアまたはドライバーのパッケージを収集することになります。収集したパッケージは、展開プロセスの一環として古いバージョンを置き換えたり更新したりするために使用します。

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-7.png)

問題を修復するリストに対する作業を進めるにつれて、さらに多くの PC が「展開準備完了」になることがわかります。つまり、PC 上のドライバーとアプリの両方が展開の対象としている Windows 10 のバージョンと互換性があることがわかるということです。

## <a name="continued-use-of-telemetry-tools"></a>テレメトリ ツールの継続使用

Windows Analytics の Upgrade Readiness は、Windows 10 および Office 365 ProPlus への移行に役立つだけのツールではありません。デスクトップで Windows 10 と Office 365 を実行している場合、このツールは、半年ごとの機能更新プログラムの展開と管理を維持して最新の状態に保つために利用できます。

## <a name="next-step"></a>次の手順 

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[手順 2: ディレクトリとネットワークの準備](https://aka.ms/mdd2)