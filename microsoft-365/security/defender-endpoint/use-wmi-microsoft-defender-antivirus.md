---
title: WMI を使用して Microsoft Defender ウイルス対策を構成する
description: WMI スクリプトを使用して Microsoft Defender for Endpoint の設定を取得、変更、および更新して、Microsoft Defender ウイルス対策を構成および管理する方法について説明します。
keywords: wmi、スクリプト、Windows 管理インストルメンテーション、構成
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 3a47a71c1d8ce416e2eacc9ca3aa47ef6c4bb499
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51749844"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a>Windows 管理インストルメンテーション (WMI) を使用して Microsoft Defender ウイルス対策を構成および管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Windows 管理インストルメンテーション (WMI) は、設定を取得、変更、および更新できるスクリプト インターフェイスです。

WMI の詳細については、「システム管理ライブラリ [Microsoft Developer Network」を参照してください](/windows/win32/wmisdk/wmi-start-page)。

Microsoft Defender Antivirus には、グループ ポリシーや他の管理ツールと同じ機能のほとんどを実行するために使用できる、複数の特定の WMI クラスがあります。 クラスの多くは [、Defender PowerShell コマンドレットに類似しています](use-powershell-cmdlets-microsoft-defender-antivirus.md)。

[MSDN Windows Defender WMIv2 Provider](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)リファレンス ライブラリには、Microsoft Defender Antivirus で使用可能な WMI クラスの一覧と、スクリプトの例が含まれています。

WMI で行われた変更は、変更が展開または行われたエンドポイントのローカル設定に影響します。 つまり、グループ ポリシー、Microsoft Endpoint Configuration Manager、または Microsoft Intune を使用してポリシーを展開すると、WMI で行われた変更が上書きされる可能性があります。 

ローカル ポリシー [の上書きを使用してローカルで上書きできる設定を構成できます](configure-local-policy-overrides-microsoft-defender-antivirus.md)。

## <a name="related-topics"></a>関連項目

- [管理および構成ツールのリファレンス トピック](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)