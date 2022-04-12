---
title: Microsoft Defender 更新プログラムの段階的ロールアウト プロセスを管理する
description: 段階的な更新プロセスと制御について説明します
keywords: 更新、更新プロセス、コントロール、リリース
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: d8a500babf581cd70b92a39b32a3be0bb5d4acd3
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789384"
---
# <a name="manage-the-gradual-rollout-process-for-microsoft-defender-updates"></a>Microsoft Defender 更新プログラムの段階的ロールアウト プロセスを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

重要な保護機能を提供し、攻撃を防ぐために、クライアント コンポーネントが最新の状態であることを確認することが重要です。

機能は、いくつかのコンポーネントを通じて提供されます。

- [エンドポイント検出&応答](overview-endpoint-detection-response.md)
- クラウド配信[保護](microsoft-defender-antivirus-windows.md)による次世代[の保護](cloud-protection-microsoft-defender-antivirus.md)
- [攻撃面の縮小](overview-attack-surface-reduction.md)

更新プログラムは、段階的なリリース プロセスを使用して毎月リリースされます。 このプロセスは、早期障害検出を有効にして、発生した影響をキャッチし、大規模なロールアウトの前に迅速に対処するのに役立ちます。

> [!NOTE]
> 毎日のセキュリティ インテリジェンス更新プログラムを制御する方法の詳細については、「[Microsoft Defender ウイルス対策保護更新プログラムをスケジュールする](manage-protection-update-schedule-microsoft-defender-antivirus.md)」を参照してください。 更新により、クラウドで配信された保護がエンドポイントで利用できない場合でも、次世代の保護が新しい脅威から保護されるようにします。

## <a name="microsoft-gradual-rollout-model"></a>Microsoft 段階的ロールアウト モデル

次の段階的ロールアウト モデルは、毎月の Defender 更新プログラムに従います。

1. 最初のリリースは、ベータ チャネルサブスクライバーに公開されます。
2. 検証、フィードバック、修正の後、調整された方法で段階的なロールアウト プロセスを開始し、最初にチャネル サブスクライバーをプレビューします。
3. その後、更新プログラムをグローバル人口の残りの部分にリリースし、10 から 100% までスケールアウトします。

エンジニアは、影響を継続的に監視し、問題をエスカレートして、必要に応じて修正を作成します。

## <a name="how-to-customize-your-internal-deployment-process"></a>内部デプロイ プロセスをカスタマイズする方法

マシンがWindows Updateから Defender 更新プログラムを受信している場合、段階的なロールアウト プロセスにより、一部のマシンが他のマシンよりも早く Defender 更新プログラムを受信する可能性があります。 次のセクションでは、更新チャネル構成を利用して、自動更新を特定のデバイス グループに異なる方法でフローできるようにする戦略を定義する方法について説明します。

> [!NOTE]
> 独自の段階的なリリースを計画する場合は、プレビューチャネルとステージングチャネルにサブスクライブしているデバイスの選択を常に用意してください。 これにより、組織と Microsoft は、環境固有の問題を防止または検出して修正する機会を提供します。

Windows Server Update Services (WSUS) や Microsoft Endpoint Configuration Manager (MECM) などの更新プログラムを受け取るマシンの場合、すべてのWindows更新プログラムで使用できるオプションが増えています。これには、次のオプションが含まれます。Microsoft Defender for Endpoint。

- WSUS、MECM などのソリューションを使用して、更新プログラムの配布とアプリケーションを管理する方法の詳細については、「[Microsoft Defender ウイルス対策更新プログラムの管理とベースラインの適用 - Windowsセキュリティ](manage-updates-baselines-microsoft-defender-antivirus.md#product-updates)」を参照してください。

## <a name="update-channels-for-monthly-updates"></a>毎月の更新プログラムのチャネルを更新する

更新チャネルにマシンを割り当てて、マシンが毎月のエンジンとプラットフォームの更新を受け取る周期を定義できます。

更新プログラムを構成する方法の詳細については、「 [Microsoft Defender 更新プログラムのカスタム 段階的ロールアウト プロセスを作成する」を](configure-updates.md)参照してください。

次の更新チャネルを使用できます。

<br>

****

|チャネル名|説明|アプリケーション|
|---|---|---|
|ベータ チャネル - プレリリース|他のユーザーより前に更新プログラムをテストする|このチャネルに設定されたデバイスは、毎月の新しい更新プログラムを受け取る最初のデバイスになります。 ベータ チャネルを選択して、Microsoft の問題の特定と報告に参加します。 Windows Insider Program のデバイスは、既定でこのチャネルにサブスクライブされます。 テスト環境でのみ使用できます。|
|最新機能提供チャネル (プレビュー)|段階的なリリース中に最新チャネルの更新プログラムを **前に** 取得する|このチャネルに設定されたデバイスには、段階的なリリース サイクルの最も早い段階で更新プログラムが提供されます。 運用前/検証前の環境に推奨されます。|
|現在のチャネル (ステージング)|段階的なリリース中に後で現在のチャネルの更新プログラムを取得する|デバイスは、段階的なリリース サイクルの後半に更新プログラムが提供されます。 デバイスの母集団の小さな代表的な部分 (~10%)に適用することをお勧めします。|
|現在のチャネル (Broad)|段階的なリリースの終了時に更新プログラムを入手する|デバイスには、段階的なリリース サイクルが完了した後にのみ更新プログラムが提供されます。 運用母集団内の広範なデバイス セット (~10 ~ 100%) に適用することをお勧めします。|
|重大: 時間の遅延|Defender の更新を遅延する|デバイスには、48 時間の遅延で更新プログラムが提供されます。 限られた更新プログラムのみを受け取るデータセンター マシンに最適です。 重要な環境にのみ推奨されます。|
|(既定値)||このポリシーを無効にするか、未構成にした場合、デバイスは現在のチャネル (既定値) に残ります。段階的なリリース サイクル中は、自動的に最新の状態を維持します。 ほとんどのデバイスに適しています。|
|

### <a name="update-channels-for-daily-updates"></a>毎日の更新プログラムのチャネルを更新する

また、コンピューターをチャネルに割り当てて、毎日の更新を受け取る周期を定義することもできます。 毎月のプロセスとは異なり、ベータ チャネルはなく、この段階的なリリース サイクルは 1 日に複数回発生します。

<br>

****

|チャネル名|説明|アプリケーション|
|---|---|---|
|現在のチャネル (ステージング)|段階的なリリース中に後で現在のチャネルの更新プログラムを取得する|デバイスは、段階的なリリース サイクルの後半に更新プログラムが提供されます。 デバイスの母集団の小さな代表的な部分 (~10%)に適用することをお勧めします。|
|現在のチャネル (Broad)|段階的なリリースの終了時に更新プログラムを入手する|デバイスには、段階的なリリース サイクルの後に更新プログラムが提供されます。 限られた更新プログラムのみを受け取るデータセンター マシンに最適です。 注: この設定は、すべての Defender 更新プログラムに適用されます。|
|(既定値)||このポリシーを無効にするか、未構成にした場合、デバイスは現在のチャネル (既定値) に残ります。段階的なリリース サイクル中は、自動的に最新の状態を維持します。 ほとんどのデバイスに適しています|
|

> [!NOTE]
> 時間の遅延を利用する代わりに、最新の署名を強制的に更新する場合は、最初にこのポリシーを削除する必要があります。

## <a name="update-guidance"></a>更新のガイダンス

ほとんどの場合、Windows Updateを使用する場合に推奨される構成は、エンドポイントが到着したときに毎月の Defender 更新プログラムを受信して適用できるようにすることです。 これにより、保護と、導入できる変更に関連する可能性のある影響との間の最適なバランスが提供されます。

Defender の自動更新をより制御された段階的なロールアウトが必要な環境の場合は、デプロイ グループのアプローチを検討してください。

1. Windows Insider プログラムに参加するか、ベータ チャネルにデバイスのグループを割り当てます。
2. プレビュー チャネル (通常は検証環境) にオプトインして、新しい更新プログラムを早期に受信するパイロット グループを指定します。
3. 段階的なチャネルからの段階的なロールアウト中に、後で更新プログラムを受け取るマシンのグループを指定します。 通常、これは人口の約 10% を表します。
4. 段階的なリリース サイクルが完了した後に更新プログラムを受け取るマシンのグループを指定します。 これらは通常、重要な運用システムです。

残りのデバイスの場合、既定の設定では、Microsoft 段階的ロールアウト プロセス中に新しい更新プログラムを受信するため、それ以上の構成は必要ありません。

このモデルを採用する:

- 運用環境に到達する前に早期リリースをテストできます
- 運用環境で引き続き定期的な更新プログラムを受け取り、重大な脅威に対する保護を確保します。

## <a name="management-tools"></a>管理ツール

毎月の更新に対して独自のカスタム 段階的ロールアウト プロセスを作成するには、次のツールを使用できます。

- グループ ポリシー
- Microsoft エンドポイント マネージャー
- PowerShell

これらのツールの使用方法の詳細については、「 [Microsoft Defender 更新プログラムのカスタム 段階的ロールアウト プロセスを作成する」を](configure-updates.md)参照してください。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS でMicrosoft Defender for Endpointの基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [IntuneのMicrosoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux でMicrosoft Defender for Endpointの基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android の機能で Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能でMicrosoft Defender for Endpointを構成する](ios-configure-features.md)