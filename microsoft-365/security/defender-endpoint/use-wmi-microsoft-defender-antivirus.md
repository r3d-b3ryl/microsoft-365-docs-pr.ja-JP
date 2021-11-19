---
title: WMI をMicrosoft Defender ウイルス対策構成する
description: Wmi スクリプトを使用して Microsoft Defender for Endpoint Microsoft Defender ウイルス対策設定を取得、変更、および更新することで、アプリケーションの構成と管理を行う方法について説明します。
keywords: wmi、スクリプト、Windows 管理インストルメンテーション、構成
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
ms.openlocfilehash: adec8350f9af0c0237e904ec0cfd37ad92649a8b
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2021
ms.locfileid: "61110561"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a>[Windows管理インストルメンテーション (WMI) を使用して、デバイスを構成および管理Microsoft Defender ウイルス対策

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Windows管理インストルメンテーション (WMI) は、設定を取得、変更、更新できるスクリプト インターフェイスです。

WMI の詳細については、「システム管理ライブラリ [Microsoft Developer Network」を参照してください](/windows/win32/wmisdk/wmi-start-page)。

Microsoft Defender ウイルス対策には、グループ ポリシーや他の管理ツールと同じ機能のほとんどを実行するために使用できる、複数の特定の WMI クラスがあります。 多くのクラスは [、Defender for Cloud PowerShell コマンドレットに類似しています](use-powershell-cmdlets-microsoft-defender-antivirus.md)。

[MSDN Windows Defender WMIv2 Provider](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)参照ライブラリには、ユーザーに使用できる WMI クラスMicrosoft Defender ウイルス対策、サンプル スクリプトが含まれています。

WMI で行われた変更は、変更が展開または行われたエンドポイントのローカル設定に影響します。 つまり、グループ ポリシー、グループ ポリシー、Microsoft Endpoint Configuration Manager、またはMicrosoft Intuneポリシーの展開は、WMI で行われた変更を上書きできます。 

ローカル ポリシー [の上書きを使用してローカルで上書きできる設定を構成できます](configure-local-policy-overrides-microsoft-defender-antivirus.md)。

## <a name="related-topics"></a>関連トピック

- [管理および構成ツールのリファレンス トピック](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
