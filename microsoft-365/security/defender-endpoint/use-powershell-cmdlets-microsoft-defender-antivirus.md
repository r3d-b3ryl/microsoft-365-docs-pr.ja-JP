---
title: PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を構成する
description: Windows 10およびWindows 11では、PowerShell コマンドレットを使用してスキャンを実行し、セキュリティ インテリジェンスを更新し、Microsoft Defender ウイルス対策の設定を変更できます。
keywords: scan, コマンド ライン, mpcmdrun, defender
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: 1cd19ff6010badd7386e937dfddb4420e76335b0
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790324"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a>PowerShell コマンドレットを使用してMicrosoft Defender ウイルス対策を構成および管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

PowerShell を使用して、Windows Defenderのさまざまな機能を実行できます。 コマンド プロンプトまたはコマンド ラインと同様に、PowerShell は、特にシステム管理用に設計されたタスクベースのコマンド ライン シェルおよびスクリプト言語です。 詳細については、 [MSDN の PowerShell ハブを参照してください](/previous-versions/msdn10/mt173057(v=msdn.10))。

コマンドレットとその機能と使用可能なパラメーターの一覧については、 [Defender ウイルス対策コマンドレット](/powershell/module/defender) のトピックを参照してください。

PowerShell コマンドレットは、グラフィカル ユーザー インターフェイス (GUI) を使用してソフトウェアを構成しないWindows サーバー環境で最も役立ちます。

> [!NOTE]
> PowerShell コマンドレットは、[Microsoft Endpoint Configuration Manager](/configmgr)、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))、Microsoft Defender ウイルス対策 グループ ポリシーなど、完全なネットワーク ポリシー管理インフラストラクチャの代わりに使用しないでください。[ ADMX テンプレート](https://www.microsoft.com/download/101445)。

PowerShell で行われた変更は、変更がデプロイまたは行われるエンドポイントのローカル設定に影響します。 つまり、グループ ポリシー、Microsoft Endpoint Configuration Manager、またはMicrosoft Intuneを使用してポリシーを展開すると、PowerShell で行われた変更が上書きされる可能性があります。

[ローカル ポリシーのオーバーライドを使用して、ローカルでオーバーライドできる設定を構成できます](configure-local-policy-overrides-microsoft-defender-antivirus.md)。

通常、PowerShell はフォルダーの下にインストールされます `%SystemRoot%\system32\WindowsPowerShell`。

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a>PowerShell コマンドレットMicrosoft Defender ウイルス対策使用する

1. Windows検索バーに **「powershell**」と入力します。
2. 結果から **Windows PowerShell** を選択してインターフェイスを開きます。
3. PowerShell コマンドと任意のパラメーターを入力します。

> [!NOTE]
> PowerShell を管理者モードで開く必要がある場合があります。 スタート メニューでアイテムを右クリックし、[**管理者として実行**] をクリックし、アクセス許可プロンプトで **[はい**] をクリックします。

いずれかのコマンドレットのオンライン ヘルプを開くには、次のように入力します。

```PowerShell
Get-Help <cmdlet> -Online
```

ローカルにキャッシュされた `-online` ヘルプを取得するには、パラメーターを省略します。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS でMicrosoft Defender for Endpointの基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [IntuneのMicrosoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux でMicrosoft Defender for Endpointの基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android の機能で Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能でMicrosoft Defender for Endpointを構成する](ios-configure-features.md)

## <a name="related-topics"></a>関連項目

- [管理および構成ツールのリファレンス トピック](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender ウイルス対策 コマンドレット](/powershell/module/defender)
