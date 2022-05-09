---
title: WMI を使用してMicrosoft Defender ウイルス対策を構成する
description: WMI スクリプトを使用してMicrosoft Defender for Endpointの設定を取得、変更、更新することで、Microsoft Defender ウイルス対策を構成および管理する方法について説明します。
keywords: wmi, スクリプト, Windows 管理インストルメンテーション, 構成
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: a525deb526f61f8500f42cc918380fdfa9c52861
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64787638"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a>Windows管理インストルメンテーション (WMI) を使用してMicrosoft Defender ウイルス対策を構成および管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

Windows Management Instrumentation (WMI) は、設定を取得、変更、更新できるスクリプト インターフェイスです。

WMI の詳細については、 [Microsoft Developer Network System Administration ライブラリ](/windows/win32/wmisdk/wmi-start-page)を参照してください。

Microsoft Defender ウイルス対策には、グループ ポリシーや他の管理ツールと同じ機能のほとんどを実行するために使用できる特定の WMI クラスが多数用意されています。 クラスの多くは、[powerShell コマンドレットDefender for Cloud](use-powershell-cmdlets-microsoft-defender-antivirus.md)に似ています。

[MSDN Windows Defender WMIv2 プロバイダー参照ライブラリ](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)には、Microsoft Defender ウイルス対策で使用可能な WMI クラスが一覧表示され、スクリプトの例が含まれています。

WMI で行われた変更は、変更がデプロイまたは行われるエンドポイントのローカル設定に影響します。 つまり、グループ ポリシー、Microsoft Endpoint Configuration Manager、またはMicrosoft Intuneを使用してポリシーを展開すると、WMI で行われた変更が上書きされる可能性があります。 

[ローカル ポリシーのオーバーライドを使用して、ローカルでオーバーライドできる設定を構成できます](configure-local-policy-overrides-microsoft-defender-antivirus.md)。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="related-topics"></a>関連項目

- [管理および構成ツールのリファレンス トピック](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
