---
title: PowerShell コマンドレットを使用して Microsoft Defender AV を構成および実行する
description: Windows 10 では、PowerShell コマンドレットを使用して、Microsoft Defender ウイルス対策でスキャンの実行、セキュリティ インテリジェンスの更新、設定の変更を行います。
keywords: scan, コマンドライン, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/23/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 912136a7229ec55b7f1644aebc946f63acb68040
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691287"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a>PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を構成および管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

PowerShell を使用して、さまざまな機能を実行Windows Defender。 コマンド プロンプトやコマンド ラインと同様に、PowerShell はタスク ベースのコマンド ライン シェルであり、特にシステム管理用に設計されたスクリプト言語です。 詳細については [、MSDN の PowerShell ハブで確認できます](/previous-versions/msdn10/mt173057(v=msdn.10))。

コマンドレットとその機能と使用可能なパラメーターの一覧については、「Defender コマンドレット」 [を参照](/powershell/module/defender) してください。

PowerShell コマンドレットは、ソフトウェアを構成するグラフィカル ユーザー インターフェイス (GUI) に依存しない Windows Server 環境で最も役立ちます。

> [!NOTE]
> PowerShell コマンドレットは [、Microsoft Endpoint Configuration Manager、](/configmgr)グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソール [、Microsoft Defender ウイルス](https://www.microsoft.com/download/101445)対策グループ ポリシー ADMX テンプレートなど、完全なネットワーク ポリシー管理インフラストラクチャの代わりとして使用する必要があります。

PowerShell で行われた変更は、変更が展開または行われたエンドポイントのローカル設定に影響します。 つまり、グループ ポリシー、Microsoft Endpoint Configuration Manager、または Microsoft Intune を使用してポリシーを展開すると、PowerShell で行われた変更が上書きされる可能性があります。

ローカル ポリシー [の上書きを使用してローカルで上書きできる設定を構成できます](configure-local-policy-overrides-microsoft-defender-antivirus.md)。

PowerShell は通常、フォルダーの下にインストールされます `%SystemRoot%\system32\WindowsPowerShell` 。

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a>Microsoft Defender ウイルス対策 PowerShell コマンドレットを使用する

1. Windows 検索バーに **「powershell」と入力します**。
2. 結果 **Windows PowerShell** を選択して、インターフェイスを開きます。
3. PowerShell コマンドとパラメーターを入力します。

> [!NOTE]
> 管理者モードで PowerShell を開く必要がある場合があります。 [スタート] メニューのアイテムを右クリックし、[管理者として実行] をクリック **し、アクセス** 許可のプロンプト **で [は** い] をクリックします。

コマンドレットのオンライン ヘルプを開く場合は、次を入力します。

```PowerShell
Get-Help <cmdlet> -Online
```

ローカルに `-online` キャッシュされたヘルプを取得するには、パラメーターを省略します。

## <a name="related-topics"></a>関連項目

- [管理および構成ツールのリファレンス トピック](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender ウイルス対策コマンドレット](/powershell/module/defender/?view=win10-ps)