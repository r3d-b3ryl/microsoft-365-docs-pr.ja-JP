---
title: Microsoft Defender ウイルス対策と Defender for Endpoint の互換性
description: Microsoft Defender for Endpoint Windows Defender動作する方法と、サードパーティのマルウェア対策クライアントを使用する場合の機能について説明します。
keywords: Windows Defender の互換性、Defender、microsoft Defender atp、エンドポイント用のディフェンダー、ウイルス対策、mde
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 63dca2694dae5dee924c9a0a02a660003907c42b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165959"
---
# <a name="microsoft-defender-antivirus-compatibility-with-microsoft-defender-for-endpoint"></a>Microsoft Defender ウイルス対策と Microsoft Defender for Endpoint の互換性

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

Microsoft Defender for Endpoint エージェントは、ファイルスキャンなどの一部の機能について Microsoft Defender ウイルス対策に依存します。

>[!IMPORTANT]
>エンドポイントの Defender は、Microsoft Defender ウイルス対策の除外設定に従う必要があります。 

Microsoft Defender ウイルス対策がアクティブなマルウェア対策かどうかに関して、Defender for Endpoint デバイスでセキュリティ インテリジェンス更新プログラムを構成する必要があります。 詳細については [、「Manage Microsoft Defender Antivirus updates and apply baselines」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md)。

オンボードデバイスがサードパーティのマルウェア対策クライアントによって保護されている場合、そのエンドポイントの Microsoft Defender Antivirus はパッシブ モードになります。

Microsoft Defender ウイルス対策は引き続き更新プログラムを受け取り *、mspeng.exe* プロセスは実行中のサービスとして表示されますが、スキャンは実行されません。実行中のサードパーティのマルウェア対策クライアントは置き換えされません。

Microsoft Defender ウイルス対策インターフェイスは無効になり、デバイス上のユーザーは Microsoft Defender ウイルス対策を使用してオンデマンド スキャンを実行したり、ほとんどのオプションを構成したりできなくなります。

詳細については、「Microsoft Defender Antivirus and Defender for Endpoint の互換性」 [を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。
