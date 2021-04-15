---
title: Microsoft Defender AV でオンデマンド スキャンを実行してカスタマイズする
description: PowerShell、Windows 管理インストルメンテーション、または Windows セキュリティ アプリを使用してエンドポイントで個別にオンデマンド スキャンを実行および構成する
keywords: スキャン、オンデマンド、dos、intune、インスタント スキャン
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/13/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 976531e1b7e1b87c4cd2dd2af66f294f68c5d4f1
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764401"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>Microsoft Defender ウイルス対策スキャンの構成と実行

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

個々のエンドポイントでオンデマンド スキャンを実行できます。 これらのスキャンはすぐに開始され、場所や種類などのスキャンのパラメーターを定義できます。

## <a name="quick-scan-versus-full-scan"></a>クイック スキャンとフル スキャン

クイック スキャンでは、レジストリ キーや既知の Windows スタートアップ フォルダーなど、システムで起動するマルウェアが登録されている可能性があるすべての場所を検索します。

> [!IMPORTANT]
> Microsoft Defender ウイルス対策は、ローカル スキャンの実行時に [LocalSystem](/windows/win32/services/localsystem-account) アカウントのコンテキストで実行されます。 ネットワーク スキャンでは、デバイス アカウントのコンテキストが使用されます。 ドメイン デバイス アカウントが共有にアクセスするための適切なアクセス許可を持ってない場合、スキャンは機能しません。 デバイスがアクセス ネットワーク共有に対するアクセス許可を持っている必要があります。

常時オン[](configure-real-time-protection-microsoft-defender-antivirus.md)のリアルタイム保護機能と組み合わせて、ファイルを開いて閉じたときに確認し、ユーザーがフォルダーに移動するたびに、クイック スキャンを実行すると、システムとカーネル レベルのマルウェアから始まるマルウェアの両方に対して強力な範囲を提供できます。  

ほとんどの場合、クイック スキャンは、リアルタイム保護によって検出されていないマルウェアを見つけるのに十分です。

フル スキャンは、マルウェアの脅威を報告したエンドポイントで役立ちます。 スキャンでは、より完全なクリーンアップを必要とする非アクティブなコンポーネントが含む場合に特定できます。 これは、組織がオンデマンド スキャンを実行している場合に最適です。

> [!NOTE]
> 既定では、USB ドライブなどのマウントされたリムーバブル デバイスでクイック スキャンが実行されます。

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>Microsoft Endpoint Manager を使用してスキャンを実行する

1. Microsoft Endpoint Manager 管理センター ( ) に移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、ログインします。
2. [エンドポイント **セキュリティウイルス**  >  **対策] を選択します**。
3. タブの一覧で、[Windows 10 の不健康な **エンドポイント] を選択します**。
4. 指定されたアクションの一覧から、[クイック スキャン] または **[フル スキャン]** **を選択します**。

[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)

> [!TIP]
> Microsoft Endpoint Manager を使用してスキャンを実行する方法の詳細については、「マルウェア対策タスクとファイアウォール タスク: オンデマンド スキャンを実行する方法」 [を参照してください](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)。

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a>スキャンをmpcmdrun.exeコマンド ライン ユーティリティを使用する

次のパラメーターを使用 `-scan` します。

```console
mpcmdrun.exe -scan -scantype 1
```

ツールの使用方法と、フル スキャンの開始、パスの定義など、追加のパラメーターの詳細については [、「microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md)を構成および管理するには、mpcmdrun.exe コマンド ライン ツールを使用する」を参照してください。

## <a name="use-microsoft-intune-to-run-a-scan"></a>Microsoft Intune を使用してスキャンを実行する

1. Microsoft Endpoint Manager 管理センター ( ) に移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、ログインします。
2. サイドバーで、[すべてのデバイス] **>選択** し、スキャンするデバイスを選択します。
3. **[..] を選択します。More**. More . オプションから、[クイック スキャン] **または [フル スキャン** ] **を選択します**。

## <a name="use-the-windows-security-app-to-run-a-scan"></a>Windows セキュリティ アプリを使用してスキャンを実行する

個々 [のエンドポイントでスキャンを実行する手順については、「Windows セキュリティ](microsoft-defender-security-center-antivirus.md) アプリでスキャンを実行する」を参照してください。

## <a name="use-powershell-cmdlets-to-run-a-scan"></a>PowerShell コマンドレットを使用してスキャンを実行する

次のコマンドレットを使用します。

```PowerShell
Start-MpScan
```

Microsoft Defender ウイルス対策で PowerShell を使用する方法の詳細については [、「Use PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) コマンドレットを使用して Microsoft Defender Antivirus コマンドレットと Defender コマンドレットを構成および実行する」を [参照してください](/powershell/module/defender/)。

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a>Windows 管理命令 (WMI) を使用してスキャンを実行する

クラスの [**Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan)メソッドを **MSFT_MpScan** します。

使用できるパラメーターの詳細については [、「WMIv2 API のWindows Defender参照してください。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策スキャン オプションの構成](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [スケジュールされた Microsoft Defender ウイルス対策スキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Windows 10 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)