---
title: Microsoft Defender 更新プログラムのカスタム 段階的ロールアウト プロセスを作成する
description: サポートされているツールを使用して、更新プログラムのカスタム 段階的ロールアウト プロセスを作成する方法について説明します
keywords: 更新ツール, GPO, intune, mdm, Microsoft エンドポイント マネージャー, policy, powershell
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
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c789f0b858f9ba55dd826f1c915668ae41553fa1
ms.sourcegitcommit: cd9df1a681265905eef99c039f7036b2fa6e8b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67276571"
---
# <a name="create-a-custom-gradual-rollout-process-for-microsoft-defender-updates"></a>Microsoft Defender 更新プログラムのカスタム 段階的ロールアウト プロセスを作成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

> [!NOTE]
> この機能には、Microsoft Defender ウイルス対策バージョン 4.18.2106.X 以降が必要です。

Defender 更新プログラムの独自のカスタム 段階的ロールアウト プロセスを作成するには、グループ ポリシー、Microsoft エンドポイント マネージャー、PowerShell を使用できます。

次の表に、更新チャネルを構成するために使用できるグループ ポリシー設定を示します。

|タイトルの設定|説明|Location|
|---|---|---|
|段階的な Microsoft Defender 月次プラットフォーム更新プログラムのロールアウト チャネルを選択する|このポリシーを有効にすると、デバイスが毎月段階的なロールアウト中に Microsoft Defender プラットフォームの更新プログラムを受け取るタイミングを指定できます。 <p> ベータ チャネル: このチャネルに設定されたデバイスは、新しい更新プログラムを受け取る最初のデバイスになります。 ベータ チャネルを選択して、Microsoft の問題の特定と報告に参加します。 Windows Insider Program のデバイスは、既定でこのチャネルにサブスクライブされます。 (手動) テスト環境でのみ使用でき、デバイスの数は限られています。 <p> 現在のチャネル (プレビュー): このチャネルに設定されたデバイスは、毎月の段階的リリース サイクルの最も早い段階で更新プログラムが提供されます。 運用前/検証前の環境に推奨されます。 <p> 現在のチャネル (段階的): デバイスは、毎月の段階的なリリース サイクルの後に更新プログラムを提供されます。 運用母集団の小さな代表的な部分 (~10%)に適用することをお勧めします。 <p> 現在のチャネル (Broad): デバイスは、段階的なリリース サイクルが完了した後にのみ更新プログラムが提供されます。 運用母集団内の広範なデバイス セット (~10 ~ 100%) に適用することをお勧めします。 <p> 重大な遅延時間: デバイスには、48 時間の遅延で更新プログラムが提供されます。 重要な環境にのみ推奨されます。 <p>このポリシーを無効にするか、未構成にした場合、段階的なリリース サイクル中にデバイスは自動的に最新の状態に維持されます。 ほとんどのデバイスに適しています。|Windows コンポーネント\Microsoft Defender ウイルス対策|
|段階的な Microsoft Defender 月次エンジン更新プログラムのロールアウト チャネルを選択する|このポリシーを有効にして、デバイスが毎月段階的なロールアウト中に Microsoft Defender エンジンの更新プログラムをいつ受信するかを指定します。 <p> ベータ チャネル: このチャネルに設定されたデバイスは、新しい更新プログラムを受け取る最初のデバイスになります。 ベータ チャネルを選択して、Microsoft の問題の特定と報告に参加します。 Windows Insider Program のデバイスは、既定でこのチャネルにサブスクライブされます。 (手動) テスト環境でのみ使用でき、デバイスの数は限られています。 <p> 現在のチャネル (プレビュー): このチャネルに設定されたデバイスは、毎月の段階的リリース サイクルの最も早い段階で更新プログラムが提供されます。 運用前/検証前の環境に推奨されます。 <p> 現在のチャネル (段階的): デバイスは、毎月の段階的なリリース サイクルの後に更新プログラムを提供されます。 運用母集団の小さな代表的な部分 (~10%)に適用することをお勧めします。 <p> 現在のチャネル (Broad): デバイスは、段階的なリリース サイクルが完了した後にのみ更新プログラムが提供されます。 運用母集団内の広範なデバイス セット (~10 ~ 100%) に適用することをお勧めします。 <p> 重大な遅延時間: デバイスには、48 時間の遅延で更新プログラムが提供されます。 重要な環境にのみ推奨されます。<p> このポリシーを無効にするか、未構成にした場合、段階的なリリース サイクル中にデバイスは自動的に最新の状態に維持されます。 ほとんどのデバイスに適しています。|Windows コンポーネント\Microsoft Defender ウイルス対策|
|段階的な Microsoft Defender 毎日のセキュリティ インテリジェンス更新プログラムのロールアウト チャネルを選択する|このポリシーを有効にして、デバイスが Microsoft Defender セキュリティ インテリジェンスの更新プログラムを毎日段階的にロールアウトするときに受信するタイミングを指定します。 <p> 現在のチャネル (段階的): デバイスは、リリース サイクル後に更新プログラムを提供されます。 運用母集団の小さな代表的な部分 (~10%)に適用することをお勧めします。 <p> 現在のチャネル (Broad): デバイスは、段階的なリリース サイクルが完了した後にのみ更新プログラムが提供されます。 運用母集団内の広範なデバイス セット (~10 ~ 100%) に適用することをお勧めします。 <p>  このポリシーを無効にするか、未構成にした場合、デバイスは毎日のリリース サイクル中に自動的に最新の状態を維持します。 ほとんどのデバイスに適しています。|Windows コンポーネント\Microsoft Defender ウイルス対策|
|Microsoft Defender 更新プログラムの段階的ロールアウトを無効にする|Defender 更新プログラムの段階的なロールアウトを無効にするには、このポリシーを有効にします。 <p> 現在のチャネル (Broad): このチャネルに設定されたデバイスは、段階的なリリース サイクル中に最後に更新プログラムが提供されます。 限られた更新プログラムのみを受け取るデータセンター マシンに最適です。 <p> 注: この設定は、毎月の Defender 更新プログラムと毎日の Defender 更新プログラムの両方に適用され、プラットフォームとエンジンの更新に対して以前に構成されたすべてのチャネルの選択がオーバーライドされます。 <p> このポリシーを無効にした場合、または構成しなかった場合、プラットフォームとエンジンの更新に対して特定のチャネルで特に指定されていない限り、デバイスは現在のチャネル (既定値) に残ります。 段階的なリリース サイクル中に自動的に最新の状態を維持します。 ほとんどのデバイスに適しています。|Windows コンポーネント\Microsoft Defender ウイルス対策\MpEngine|
|

## <a name="group-policy"></a>グループ ポリシー

> [!NOTE]
> 更新された Defender ADMX テンプレートは、Windows 10の 21H2 リリースと共に公開されます。 ローカライズされていないバージョンは、次の場所で https://github.com/microsoft/defender-updatecontrolsダウンロードできます。

[グループ ポリシー](/windows/win32/srvnodes/group-policy?redirectedfrom=MSDN)を使用して、エンドポイントで Microsoft Defender ウイルス対策を構成および管理できます。

一般に、次の手順を使用して、Microsoft Defender ウイルス対策グループ ポリシー設定を構成または変更できます。

1. グループ ポリシー管理マシンで、**グループ ポリシー管理コンソール** を開き、構成する **グループ ポリシー オブジェクト** (GPO) を右クリックし、[編集] をクリック **します**。

2. グループ ポリシー管理エディターを使用して **、コンピューターの構成** に移動します。

3. [ **管理用テンプレート]** をクリックします。

4. **ツリーを Microsoft Defender ウイルス対策> Windows コンポーネントに展開します**。

5. 構成する設定を含むセクション (このトピックの「 **場所** 」と呼ばれます) を展開し、設定をダブルクリックして開き、構成を変更します。

6. [通常どおりに、更新された GPO をデプロイ](https://msdn.microsoft.com/library/ee663280(v=vs.85).aspx)します。

## <a name="intune"></a>Intune

次のリンクの手順に従って、Intuneでカスタム ポリシーを作成します。

[Microsoft IntuneでWindows 10 デバイスのカスタム設定を追加する - Azure \|Microsoft Docs](/mem/intune/configuration/custom-settings-windows-10)

段階的なロールアウト プロセスに使用される Defender CSP の詳細については、「 [Defender CSP](/windows/client-management/mdm/defender-csp)」を参照してください。

## <a name="powershell"></a>PowerShell

コマンドレットを `Set-MpPreference` 使用して、段階的な更新プログラムのロールアウトを構成します。

次のパラメーターを使用します:

```powershell
Set-MpPreference
-PlatformUpdatesChannel Beta|Preview|Staged|Broad|Delayed|NotConfigured
-EngineUpdatesChannel Beta|Preview|Staged|Broad|Delayed|NotConfigured
-DisableGradualRelease 1|0
-SignaturesUpdatesChannel Staged|Broad|NotConfigured
```

例:

ベータ チャネルから到着するようにプラットフォームの更新プログラムを構成するために使用 `Set-MpPreference -PlatformUpdatesChannel Beta` します。

パラメーターとその構成方法の詳細については、「 [Set-MpPreference](/powershell/module/defender/set-mppreference) (Microsoft Defender ウイルス対策)」を参照してください。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)
