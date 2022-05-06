---
title: アプリケーション/テストルール
description: アプリケーション/テストのアップロード時に従うルール
search.appverid: MET150
author: andreicsibi-msft
ms.author: ancsibi
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 02/04/2022
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: cebf888d7a17d6d589888d529cea1731b666f562
ms.sourcegitcommit: 954c8af658adb270fe843991e048c6a30e86e77c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2022
ms.locfileid: "62429023"
---
# <a name="applicationtest-rules"></a>アプリケーション/テストルール

Test Base のすべてのアプリケーションまたはテストは、次の規則に従う必要があります。

## <a name="test-base-folders"></a>基本フォルダーをテストする 

Test Base インフラストラクチャでは、次のフォルダーが使用されます。
* %SYSTEMDRIVE%\USL
* %SYSTEMDRIVE%\EtlExport
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
> **次の手順は避けてください**。
> * これらのフォルダーから任意のプロセスの実行をブロックします。 アプリケーションがマルウェア対策ソフトウェアの場合は、これらのフォルダーからのすべてのプロセスを妨げない実行を許可するようにアプリのインストールを構成します。
> * これらのフォルダーの改ざん。

## <a name="test-base-registry-keys"></a>基本レジストリ キーをテストする

アプリケーション/テストでは、次に関連するレジストリ キーを削除または変更しないでください。
* Windowsテレメトリ レベル
* TLS 1.2 の削除
