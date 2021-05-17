---
title: オンデマンド スキャンを実行してカスタマイズする方法は、Microsoft Defender ウイルス対策
description: PowerShell、Windows 管理インストルメンテーション、またはアプリを使用してエンドポイントで個別にオンデマンド スキャンを実行Windows セキュリティする
keywords: スキャン、オンデマンド、dos、intune、インスタント スキャン
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/05/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 124ebde48c008743a486a4454e7772fd93f9eca7
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275362"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>オンデマンドの Microsoft Defender ウイルス対策スキャンを構成して実行する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

個々のエンドポイントでオンデマンド スキャンを実行できます。 これらのスキャンはすぐに開始され、場所や種類などのスキャンのパラメーターを定義できます。

## <a name="quick-scan-versus-full-scan"></a>クイック スキャンとフル スキャン

クイック スキャンは、レジストリ キーや既知のスタートアップ フォルダーなど、システムで開始するマルウェアが登録されている可能性があるすべての場所Windowsします。

> [!IMPORTANT]
> Microsoft Defender ウイルス対策スキャンを実行するときに[、LocalSystem](/windows/win32/services/localsystem-account)アカウントのコンテキストで実行されます。 ネットワーク スキャンでは、デバイス アカウントのコンテキストが使用されます。 ドメイン デバイス アカウントが共有にアクセスするための適切なアクセス許可を持ってない場合、スキャンは機能しません。 デバイスがアクセス ネットワーク共有に対するアクセス許可を持っている必要があります。

常時オン[](configure-real-time-protection-microsoft-defender-antivirus.md)のリアルタイム保護機能と組み合わせて、ファイルを開いて閉じたときに確認し、ユーザーがフォルダーに移動するたびに、クイック スキャンを実行すると、システムとカーネル レベルのマルウェアから始まるマルウェアの両方に対して強力な範囲を提供できます。  

ほとんどの場合、クイック スキャンは、リアルタイム保護によって検出されていないマルウェアを見つけるのに十分です。

フル スキャンは、マルウェアの脅威を報告したエンドポイントで役立ちます。 スキャンでは、より完全なクリーンアップを必要とする非アクティブなコンポーネントが含む場合に特定できます。 これは、組織がオンデマンド スキャンを実行している場合に最適です。

> [!NOTE]
> 既定では、USB ドライブなどのマウントされたリムーバブル デバイスでクイック スキャンが実行されます。

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>スキャンMicrosoft エンドポイント マネージャー実行するには、次のコマンドを使用します。

1. 管理センター ( ) Microsoft エンドポイント マネージャーに移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、ログインします。
2. [エンドポイント **セキュリティウイルス**  >  **対策] を選択します**。
3. タブの一覧で、[不健康 **なWindows 10を選択します**。
4. 指定されたアクションの一覧から、[クイック スキャン] または **[フル スキャン]** **を選択します**。

[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)

> [!TIP]
> スキャンの実行に Microsoft エンドポイント マネージャーの詳細については、「マルウェア対策タスクとファイアウォール タスク: オンデマンド スキャンを実行する[方法」を参照してください](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)。

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a>スキャンをmpcmdrun.exeコマンド ライン ユーティリティを使用する

次のパラメーターを使用 `-scan` します。

```console
mpcmdrun.exe -scan -scantype 1
```

ツールの使用方法と、フル スキャンの開始、パスの定義など、追加のパラメーターの詳細については、「mpcmdrun.exe コマンド ライン ツールを使用して、Microsoft Defender ウイルス対策 を構成および管理する」[を参照してください](command-line-arguments-microsoft-defender-antivirus.md)。

## <a name="use-microsoft-intune-to-run-a-scan"></a>スキャンMicrosoft Intune実行するには、次のコマンドを使用します。

1. 管理センター ( ) Microsoft エンドポイント マネージャーに移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、ログインします。
2. サイドバーで、[すべてのデバイス] **>選択** し、スキャンするデバイスを選択します。
3. **[..] を選択します。More**. More . オプションから、[クイック スキャン] **または [フル スキャン** ] **を選択します**。

## <a name="use-the-windows-security-app-to-run-a-scan"></a>スキャンを実行Windows セキュリティアプリを使用する

個々[のエンドポイントでスキャン](microsoft-defender-security-center-antivirus.md)を実行する方法については、「Windows セキュリティ アプリでスキャンを実行する」を参照してください。

## <a name="use-powershell-cmdlets-to-run-a-scan"></a>PowerShell コマンドレットを使用してスキャンを実行する

次のコマンドレットを使用します。

```PowerShell
Start-MpScan
```

PowerShell を Microsoft Defender ウイルス対策と一緒に使用する方法の詳細については[、「Use PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)コマンドレットを使用して、PowerShell コマンドレットと Defender コマンドレットを構成およびMicrosoft Defender ウイルス対策実行する」を[参照してください](/powershell/module/defender/)。

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a>スキャンWindows実行するには、管理命令 (WMI) を使用します。

クラスの [**Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan)メソッドを **MSFT_MpScan** します。

使用できるパラメーターの詳細については[、「WMIv2 API のWindows Defender参照してください。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策スキャン オプションを構成する](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [スケジュールされたスキャンMicrosoft Defender ウイルス対策構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)