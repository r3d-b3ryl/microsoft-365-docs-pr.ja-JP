---
title: ハードウェア ベースの分離 (Windows 10)
ms.reviewer: ''
description: Windows 10 でのハードウェア ベースの分離がマルウェア対策に役立つ方法について学習します。
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.author: macapara
ms.date: 09/07/2018
ms.technology: mde
ms.openlocfilehash: b31db39e03ed23698e71c4b38fb0937d2ba59727
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060952"
---
# <a name="hardware-based-isolation-in-windows-10"></a>Windows 10 でのハードウェア ベースの分離

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


ハードウェア ベースの分離は、Windows 10 のシステム整合性を保護するのに役立ち、Microsoft Defender for Endpoint と統合されています。 

| 機能 | 説明 |
|------------|-------------|
| [Windows Defender Application Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview.md) | Application Guard は、生産性を維持しながら、高度な攻撃からデバイスを保護します。 独自のハードウェア ベースの分離アプローチを使用して、信頼されていない Web サイトと PDF ドキュメントを、ネイティブの Windows ハイパーバイザーを介してオペレーティング システムから分離された軽量コンテナー内で分離することです。 信頼されていないサイトまたは PDF ドキュメントが悪意のあると判明した場合でも、デスクトップ PC を保護し、攻撃者をエンタープライズ データから遠く離して、Application Guard のセキュリティで保護されたコンテナーに含まれるままです。 |
| [Windows Defender System Guard](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows.md) | System Guard は、システムの開始および実行後にシステムの整合性を保護および維持し、構成証明を使用してシステムの整合性を検証します。  |

