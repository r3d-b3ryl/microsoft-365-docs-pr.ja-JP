---
title: Defender for Endpoint とのウイルス対策ソリューションの互換性
description: Microsoft Defender for Endpoint Windows Defender動作する方法と、サードパーティのマルウェア対策クライアントを使用する場合の機能について説明します。
keywords: Windows Defender の互換性、Defender、Microsoft Defender for Endpoint、Defender for endpoint、ウイルス対策、mde
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
ms.date: 05/06/2021
ms.technology: mde
ms.openlocfilehash: 744b68d3cbb910eca3d3cd5d47d94feb3581ae7c
ms.sourcegitcommit: 87d994407fb69a747239b8589ad11ddf9b47e527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2021
ms.locfileid: "53595680"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint とのウイルス対策ソリューションの互換性

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

Microsoft Defender for Endpoint エージェントは、ファイルMicrosoft Defender ウイルス対策機能の種類によって異なります。

>[!IMPORTANT]
>エンドポイントの Defender は、[除外] のMicrosoft Defender ウイルス対策に従う必要があります。 

Defender for Endpoint デバイスでセキュリティ インテリジェンスの更新プログラムを構成する必要があります。Microsoft Defender ウイルス対策がアクティブなマルウェア対策であるかどうかを指定します。 詳細については、「更新プログラムの[管理と基準Microsoft Defender ウイルス対策適用する」を参照してください](manage-updates-baselines-microsoft-defender-antivirus.md)。

オンボードデバイスがサードパーティのマルウェア対策クライアントによって保護されている場合、そのエンドポイントのMicrosoft Defender ウイルス対策はパッシブ モードになります。

Microsoft Defender ウイルス対策は更新プログラムを受信し続け *、mspeng.exe* プロセスは実行中のサービスとして表示されますが、スキャンは実行されません。実行中のサードパーティのマルウェア対策クライアントは置き換えされません。

インターフェイスMicrosoft Defender ウイルス対策無効になり、デバイス上のユーザーはオンデマンド スキャンを実行したり、ほとんどのオプションを構成したりするために Microsoft Defender ウイルス対策を使用できなくなります。

詳細については、「エンドポイントの互換性」Microsoft Defender ウイルス対策[Defender のトピックを参照してください](microsoft-defender-antivirus-compatibility.md)。
