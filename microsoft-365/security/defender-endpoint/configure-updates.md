---
title: Microsoft Defender 更新プログラムのカスタム段階的ロールアウト プロセスを作成する
description: サポートされているツールを使用して、更新プログラムのカスタム段階的ロールアウト プロセスを作成する方法について説明します。
keywords: 更新ツール, gpo, intune, mdm, microsoft エンドポイント マネージャー, ポリシー, powershell
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 523a73477343bc9face75bcceda1ed603d1f6439
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2021
ms.locfileid: "60704633"
---
# <a name="create-a-custom-gradual-rollout-process-for-microsoft-defender-updates"></a>Microsoft Defender 更新プログラムのカスタム段階的ロールアウト プロセスを作成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> この機能には、Microsoft Defender ウイルス対策バージョン 4.18.2106.X 以降が必要です。

Defender 更新プログラム用に独自のカスタム段階的ロールアウト プロセスを作成するには、グループ ポリシー、グループ ポリシー、Microsoft エンドポイント マネージャー PowerShell を使用できます。

次の表に、更新プログラム チャネルを構成するための使用可能なグループ ポリシー設定を示します。

<br>

****

|タイトルの設定|説明|Location|
|---|---|---|
|段階的な Microsoft Defender の月次プラットフォーム更新プログラムのロールアウト チャネルを選択する|このポリシーを有効にして、毎月段階的なロールアウト中にデバイスが Microsoft Defender プラットフォームの更新プログラムを受信する時間を指定します。 <p> ベータ チャネル: このチャネルに設定されているデバイスは、新しい更新プログラムを最初に受信します。 [ベータ チャネル] を選択して、Microsoft への問題の特定と報告に参加します。 Insider Program Windowsデバイスは、既定でこのチャネルにサブスクライブされます。 (手動) テスト環境でのみ使用し、デバイスの数が限られている場合。 <p> 現在のチャネル (プレビュー): このチャネルに設定されているデバイスは、毎月の段階的なリリース サイクルで最も早く更新プログラムが提供されます。 実稼働前/検証前の環境で推奨されます。 <p> 現在のチャネル (段階的): デバイスは、毎月の段階的なリリース サイクルの後に更新プログラムが提供されます。 生産人口の小さな代表的な部分 (~10%)に適用する必要があります。 <p> 現在のチャネル (Broad): 段階的なリリース サイクルが完了した後にのみ、デバイスに更新プログラムが提供されます。 実稼働人口 (~10~100%)の幅広いデバイスセットに適用する必要があります。 <p> クリティカルタイム遅延: デバイスには、48 時間の遅延で更新プログラムが提供されます。 重要な環境にのみ推奨されます。 <p>このポリシーを無効にするか構成しない場合、デバイスは段階的なリリース サイクル中に自動的に最新の情報を残します。 ほとんどのデバイスに適しています。|WindowsComponents\Microsoft Defender ウイルス対策|
|段階的な Microsoft Defender の毎月のエンジン更新プログラムのロールアウト チャネルを選択する|このポリシーを有効にして、毎月段階的なロールアウト中にデバイスが Microsoft Defender エンジンの更新プログラムを受信する時間を指定します。 <p> ベータ チャネル: このチャネルに設定されているデバイスは、新しい更新プログラムを最初に受信します。 [ベータ チャネル] を選択して、Microsoft への問題の特定と報告に参加します。 Insider Program Windowsデバイスは、既定でこのチャネルにサブスクライブされます。 (手動) テスト環境でのみ使用し、デバイスの数が限られている場合。 <p> 現在のチャネル (プレビュー): このチャネルに設定されているデバイスは、毎月の段階的なリリース サイクルで最も早く更新プログラムが提供されます。 実稼働前/検証前の環境で推奨されます。 <p> 現在のチャネル (段階的): デバイスは、毎月の段階的なリリース サイクルの後に更新プログラムが提供されます。 生産人口の小さな代表的な部分 (~10%)に適用する必要があります。 <p> 現在のチャネル (Broad): 段階的なリリース サイクルが完了した後にのみ、デバイスに更新プログラムが提供されます。 実稼働人口 (~10~100%)の幅広いデバイスセットに適用する必要があります。 <p> クリティカルタイム遅延: デバイスには、48 時間の遅延で更新プログラムが提供されます。 重要な環境にのみ推奨されます。<p> このポリシーを無効にするか構成しない場合、デバイスは段階的なリリース サイクル中に自動的に最新の情報を残します。 ほとんどのデバイスに適しています。|WindowsComponents\Microsoft Defender ウイルス対策|
|段階的な Microsoft Defender の毎日のセキュリティ インテリジェンス更新プログラムのロールアウト チャネルを選択する|このポリシーを有効にして、デバイスが毎日の段階的なロールアウト中に Microsoft Defender セキュリティ インテリジェンス更新プログラムを受信する時間を指定します。 <p> 現在のチャネル (Staged): デバイスは、リリース サイクル後に更新プログラムを提供されます。 生産集団の小さな代表的な部分 (~10%)に適用する必要があります。 <p> 現在のチャネル (Broad): 段階的なリリース サイクルが完了した後にのみ、デバイスに更新プログラムが提供されます。 実稼働人口 (~10~100%)の幅広いデバイスセットに適用する必要があります。 <p>  このポリシーを無効にするか構成しない場合、デバイスは毎日のリリース サイクル中に自動的に最新の情報を残します。 ほとんどのデバイスに適しています。|WindowsComponents\Microsoft Defender ウイルス対策|
|Microsoft Defender 更新プログラムの段階的なロールアウトを無効にする|Defender 更新プログラムの段階的なロールアウトを無効にするには、このポリシーを有効にします。 <p> 現在のチャネル (Broad): このチャネルに設定されたデバイスは、段階的なリリース サイクルの最後に更新プログラムが提供されます。 制限付き更新プログラムのみを受信するデータセンター コンピューターに最適です。 <p> 注: この設定は、毎月の Defender 更新プログラムと毎日の Defender 更新プログラムの両方に適用され、プラットフォームとエンジンの更新に対して以前に構成されたチャネルの選択を上書きします。 <p> このポリシーを無効にするか構成しない場合、プラットフォームおよびエンジン更新プログラムの特定のチャネルで特に指定されていない限り、デバイスは現在のチャネル (既定) に残ります。 段階的なリリース サイクル中に自動的に最新の情報を残します。 ほとんどのデバイスに適しています。|WindowsComponents\Microsoft Defender ウイルス対策|
|

## <a name="group-policy"></a>グループ ポリシー

> [!NOTE]
> 更新された Defender ADMX テンプレートは、21H2 リリースのバージョンと共に公開Windows 10。 ローカライズされていないバージョンはでダウンロードできます https://github.com/microsoft/defender-updatecontrols 。

グループ ポリシーを[使用して](/windows/win32/srvnodes/group-policy?redirectedfrom=MSDN)、エンドポイントのMicrosoft Defender ウイルス対策管理できます。

一般に、次の手順を使用して、グループ ポリシー設定を構成Microsoft Defender ウイルス対策変更できます。

1. グループ ポリシー管理マシンで、グループ ポリシー **管理** コンソールを開き、構成するグループ ポリシー オブジェクト **(GPO)** を右クリックし、[編集] をクリック **します**。

2. グループ ポリシー管理エディターを使用して、[コンピューターの構成] **に移動します**。

3. [管理 **用テンプレート] をクリックします**。

4. ツリーを展開して **、Windowsコンポーネント> Microsoft Defender ウイルス対策。**

5. 構成する設定を含むセクション(このトピックの表では Location と呼ばれます) を展開し、設定をダブルクリックして開き、構成を変更します。

6. [通常と同じ方法で更新された GPO を展開します](https://msdn.microsoft.com/library/ee663280(v=vs.85).aspx)。

## <a name="intune"></a>Intune

Intune でカスタム ポリシーを作成するには、以下のリンクの手順に従います。

[Azure Microsoft Docs - Windows 10デバイスMicrosoft Intuneカスタム設定 \| を追加する](/mem/intune/configuration/custom-settings-windows-10)

段階的なロールアウト プロセスで使用される Defender CSP の詳細については [、「Defender CSP」を参照してください](/windows/client-management/mdm/defender-csp)。

## <a name="powershell"></a>PowerShell

段階的な `Set-MpPreference` 更新プログラムのロールアウトを構成するには、コマンドレットを使用します。

次のパラメーターを使用します:

```powershell
Set-MpPreference
-PlatformUpdatesChannel Beta|Preview|Staged|Broad|Delayed|NotConfigured
-EngineUpdatesChannel Beta|Preview|Staged|Broad|Delayed|NotConfigured
-DisableGradualRelease True|False
-SignaturesUpdatesChannel Staged|Broad|NotConfigured
```

例:

ベータ `Set-MpPreference -PlatformUpdatesChannel Beta` チャネルから届くプラットフォーム更新プログラムを構成するために使用します。

パラメーターの詳細と構成方法については [、「Set-MpPreference (Defender)」を参照|Microsoft Docs](/powershell/module/defender/set-mppreference).
