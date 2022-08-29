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
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: tinachen
f1.keywords: NOCSH
ms.openlocfilehash: 6a3878e0326fdcfe1ea9d35997e6a605457fcbf7
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2022
ms.locfileid: "67316492"
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
* Windows テレメトリ レベル
* TLS 1.2 の削除
