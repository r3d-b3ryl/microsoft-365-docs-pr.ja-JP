---
title: アプリケーション/テスト ルール
description: アプリケーション/テストのアップロード時に従うルール
search.appverid: MET150
author: andreicsibi-msft
ms.author: ancsibi
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 66f5557f6183cb3691982079c4afd97b1b5dfe85
ms.sourcegitcommit: cde34d38bdfb6335b980f1c48c6b218da6a64bf8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2022
ms.locfileid: "62156595"
---
# <a name="applicationtest-rules"></a>アプリケーション/テスト ルール

Test Base のすべてのアプリケーションまたはテストは、次のルールに従う必要があります。

## <a name="test-base-folders"></a>基本フォルダーのテスト 

Test Base インフラストラクチャでは、次のフォルダーが使用されます。
* %SYSTEMDRIVE%\USL
* %SYSTEMDRIVE%\Ffmpeg
* %SYSTEMDRIVE%\Monitoring
* %SYSTEMDRIVE%\powershell-yaml
* %SYSTEMDRIVE%\ProcMon
* %SYSTEMDRIVE%\PSTools
* %SYSTEMDRIVE%\TokenProviderTool
* %SYSTEMDRIVE%\USLPowershellModules
* %SYSTEMDRIVE%\UtcUtil
* %SYSTEMDRIVE%\WPT
* %SYSTEMDRIVE%\WULogs

> [!IMPORTANT]
> **次の問題を回避します**。
> * これらのフォルダーから任意のプロセスの実行をブロックします。 アプリケーションがマルウェア対策ソフトウェアの場合は、これらのフォルダーからのすべてのプロセスの実行を許可するアプリ のインストールを構成します。
> * これらのフォルダーの改ざん。

## <a name="test-base-registry-keys"></a>Test Base レジストリ キー

アプリケーション/テストは、次に関連するレジストリ キーを削除したり変更したりしな
* Windowsテレメトリ レベル
* TLS 1.2 の削除
