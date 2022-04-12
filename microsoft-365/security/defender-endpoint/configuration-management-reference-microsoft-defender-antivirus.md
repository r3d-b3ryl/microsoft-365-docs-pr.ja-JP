---
title: ビジネスのMicrosoft Defender ウイルス対策を管理する
description: グループ ポリシー、Configuration Manager、PowerShell、WMI、Intune、およびコマンド ラインを使用して Microsoft Defender AV を管理する方法について説明します
keywords: グループ ポリシー, GPO, config manager, sccm, scep, powershell, wmi, intune, defender, ウイルス対策, マルウェア対策, セキュリティ, 保護
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 76f6f1cda9b2def0c18be8c368da15645994eece
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64787976"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a>ビジネスのMicrosoft Defender ウイルス対策を管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

次のツールを使用して、Microsoft Defender ウイルス対策を管理および構成できます。

- [Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (現在はMicrosoft エンドポイント マネージャーの一部)
- [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (現在はMicrosoft エンドポイント マネージャーの一部)
- [グループ ポリシー](./use-group-policy-microsoft-defender-antivirus.md)
- [PowerShell コマンドレット](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Windows Management Instrumentation (WMI)](./use-wmi-microsoft-defender-antivirus.md)
- [Microsoft Malware Protection コマンド ライン ユーティリティ](./command-line-arguments-microsoft-defender-antivirus.md) (*mpcmdrun.exe* ユーティリティと呼ばれます)

次の記事では、これらのツールを使用してMicrosoft Defender ウイルス対策を管理および構成するための詳細情報、リンク、リソースについて説明します。

|記事|説明|
|:---|:---|
|[Microsoft IntuneとMicrosoft Endpoint Configuration ManagerでMicrosoft Defender ウイルス対策を管理する](use-intune-config-manager-microsoft-defender-antivirus.md)|IntuneとConfiguration Managerを使用してMicrosoft Defender ウイルス対策をデプロイ、管理、レポート、および構成する方法に関する情報|
|[グループ ポリシー設定でMicrosoft Defender ウイルス対策を管理する](use-group-policy-microsoft-defender-antivirus.md)|ADMX テンプレートにあるすべてのグループ ポリシー設定の一覧|
|[PowerShell コマンドレットを使用してMicrosoft Defender ウイルス対策を管理する](use-powershell-cmdlets-microsoft-defender-antivirus.md)|PowerShell コマンドレットを使用してMicrosoft Defender ウイルス対策を管理する手順と、すべてのコマンドレットと許可されるパラメーターのドキュメントへのリンク|
|[Windows管理インストルメンテーション (WMI) を使用してMicrosoft Defender ウイルス対策を管理する](use-wmi-microsoft-defender-antivirus.md)|WMI を使用してMicrosoft Defender ウイルス対策を管理する手順と、WMIv2 API のドキュメントへのリンク (すべてのクラス、メソッド、プロパティを含む)|
|[MpCmdRun.exe コマンド ライン ツールを使用してMicrosoft Defender ウイルス対策を管理する](command-line-arguments-microsoft-defender-antivirus.md)|専用コマンド ライン ツールを使用してMicrosoft Defender ウイルス対策を管理および使用する手順|

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS でMicrosoft Defender for Endpointの基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [IntuneのMicrosoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux でMicrosoft Defender for Endpointの基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android の機能で Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能でMicrosoft Defender for Endpointを構成する](ios-configure-features.md)