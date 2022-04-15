---
title: Microsoft Defender for Endpointをリングにデプロイする
description: Microsoft Defender for Endpointをリングにデプロイする方法について説明します
keywords: デプロイ, リング, 評価, パイロット, insider fast, insider slow, セットアップ, オンボード, フェーズ, デプロイ, デプロイ, 導入, 構成
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e308b1c1d8c26a4ec3d6b3044501ffe1ce92e1c7
ms.sourcegitcommit: e3bc6563037bd2cce2abf108b3d1bcc2ccf538f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2022
ms.locfileid: "64862886"
---
# <a name="deploy-microsoft-defender-for-endpoint-in-rings"></a>Microsoft Defender for Endpointをリングにデプロイする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Microsoft Defender for Endpointのデプロイは、リングベースのデプロイ アプローチを使用して行うことができます。

デプロイ リングは、次のシナリオで適用できます。

- [新しいデプロイ](#new-deployments)
- [既存のデプロイ](#existing-deployments)

## <a name="new-deployments"></a>新しいデプロイ

:::image type="content" source="images/deployment-rings.png" alt-text="デプロイリング。" lightbox="images/deployment-rings.png":::

リングベースのアプローチは、オンボードする一連のエンドポイントを特定し、サービスを大規模な一連のデバイスにデプロイする前に特定の条件が満たされていることを確認する方法です。 各リングの終了条件を定義し、次のリングに移動する前にそれらが満たされていることを確認できます。

リングベースのデプロイを採用すると、サービスのロールアウト中に発生する可能性がある潜在的な問題を減らすことができます。 最初に特定の数のデバイスをパイロットすることで、潜在的な問題を特定し、発生する可能性のある潜在的なリスクを軽減できます。

表 1 に、使用する可能性のあるデプロイ リングの例を示します。

**表 1**:

|展開リング|説明|
|---|---|
|評価|リング 1: パイロット テスト用の 50 システムを特定する|
|パイロット|リング 2: 運用環境で次の 50 ~ 100 個のエンドポイントを特定する|
|完全な展開|リング 3: サービスを他の環境に大きく段階的にロールアウトする|

### <a name="exit-criteria"></a>終了条件

これらのリングの終了条件のセットの例を次に示します。

- デバイス インベントリの一覧にデバイスが表示される
- アラートがダッシュボードに表示される
- [検出テストの実行](run-detection-test.md)
- [デバイスに対してシミュレートされた攻撃を実行する](attack-simulations.md)

### <a name="evaluate"></a>評価

サービスにオンボードする環境内の少数のテスト マシンを特定します。 理想的には、これらのマシンのエンドポイントは 50 個未満です。

### <a name="pilot"></a>パイロット

Microsoft Defender for Endpointでは、サービスにオンボードできるさまざまなエンドポイントがサポートされています。 このリングで、オンボードする複数のデバイスを特定し、定義した終了条件に基づいて、次の展開リングに進みます。

次の表は、サポートされているエンドポイントと、デバイスをサービスにオンボードするために使用できる対応するツールを示しています。

|エンドポイント|デプロイ ツール|
|---|---|
|**Windows**|[ローカル スクリプト (最大 10 台のデバイス)](configure-endpoints-script.md) <br> 注: 運用環境に 10 台を超えるデバイスをデプロイする場合は、代わりに グループ ポリシー メソッドを使用するか、以下に示す他のサポートされているツールを使用します。<br>  [グループ ポリシー](configure-endpoints-gp.md) <br>  [Microsoft エンドポイント マネージャー/ モバイル デバイス マネージャー](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI スクリプト](configure-endpoints-vdi.md) <br> [Microsoft Defender for Cloudとの統合](configure-server-endpoints.md#integration-with-microsoft-defender-for-cloud) |
|**macOS**|[ローカル スクリプト](mac-install-manually.md) <br> [Microsoft エンドポイント マネージャー](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [モバイル デバイス管理](mac-install-with-other-mdm.md)|
|**Linux Server**|[ローカル スクリプト](linux-install-manually.md) <br> [人形](linux-install-with-puppet.md) <br> [アンシブル](linux-install-with-ansible.md)|
|**iOS**|[Microsoft エンドポイント マネージャー](ios-install.md)|
|**Android**|[Microsoft エンドポイント マネージャー](android-intune.md)|

### <a name="full-deployment"></a>完全な展開

この段階では、デプロイ計画の資料を使用して [、デプロイ](deployment-strategy.md) の計画に役立ちます。

次の資料を使用して、組織に最適な適切なMicrosoft Defender for Endpointアーキテクチャを選択します。

|アイテム|説明|
|---|---|
|[:::image type="content" source="images/mde-deployment-strategy.png" alt-text="Microsoft Defender for Endpointデプロイの戦略。" lightbox="images/mde-deployment-strategy.png":::](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)<br/> [PDF](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf) \| [Visio](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx)|アーキテクチャ教材は、次のアーキテクチャの展開を計画するのに役立ちます。 <ul><li> クラウド-ネイティブ </li><li> 共同管理 </li><li> オンプレミス</li><li>評価とローカル オンボード</li></ul>|

## <a name="existing-deployments"></a>既存のデプロイ

### <a name="windows-endpoints"></a>エンドポイントをWindowsする

WindowsサーバーまたはWindows サーバーの場合は、**セキュリティ更新プログラム (SUVP**) を使用して、事前にテストするマシン (火曜日のパッチの前) を選択します。

詳細については、以下を参照してください。

- [セキュリティ更新プログラムの検証プログラムとは](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/what-is-the-security-update-validation-program/ba-p/275767)
- [ソフトウェア更新プログラムの検証プログラムとMicrosoft マルウェア プロテクション センターの確立 - TwC 対話型タイムライン パート 4](https://www.microsoft.com/security/blog/2012/03/28/software-update-validation-program-and-microsoft-malware-protection-center-establishment-twc-interactive-timeline-part-4/)

### <a name="non-windows-endpoints"></a>Windows以外のエンドポイント

macOS と Linux では、いくつかのシステムを使用してベータ チャネルで実行できます。

> [!NOTE]
> ビルドで現在のチャネルに移行する前に互換性、パフォーマンス、信頼性の問題を見つけることができるように、少なくとも 1 人のセキュリティ管理者と 1 人の開発者が理想的です。

チャネルの選択により、デバイスに提供される更新プログラムの種類と頻度が決まります。 ベータ版のデバイスは、更新プログラムと新機能を受け取る最初のデバイスであり、後でプレビュー、最後に Current が続きます。

:::image type="content" source="images/insider-rings.png" alt-text="インサイダー リング。" lightbox="images/insider-rings.png":::

新機能をプレビューし、早期のフィードバックを提供するには、ベータ版またはプレビュー版を使用するように企業内の一部のデバイスを構成することをお勧めします。

> [!WARNING]
> 初期インストール後にチャネルを切り替えるには、製品を再インストールする必要があります。製品チャネルを切り替えるには: 既存のパッケージをアンインストールし、新しいチャネルを使用するようにデバイスを再構成し、このドキュメントの手順に従って新しい場所からパッケージをインストールします。
