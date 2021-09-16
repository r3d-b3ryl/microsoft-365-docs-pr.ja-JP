---
title: ハードウェア ベースの分離 (Windows 10)
ms.reviewer: ''
description: マルウェア対策に役立つハードウェア ベースの分離Windows 10について学習します。
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
ms.openlocfilehash: 06d07b6457e57f6693e029c9ecccf1ca7f90b0cc
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2021
ms.locfileid: "59401628"
---
# <a name="hardware-based-isolation-in-windows-10"></a>Windows 10 のハードウェア ベースの分離

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](/security/defender-endpoint)
- [Microsoft 365 Defender](/security/defender/microsoft-365-defender)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

ハードウェア ベースの分離は、Microsoft Defender for Endpoint と統合Windows 10システムの整合性を保護するのに役立ちます。

<br>

****

|機能|説明|
|---|---|
|[Windows Defender Application Guard](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview)|Application Guard は、生産性を維持しながら、高度な攻撃からデバイスを保護します。 独自のハードウェア ベースの分離アプローチを使用して、信頼されていない Web サイトと PDF ドキュメントを、ネイティブの Windows ハイパーバイザーを介してオペレーティング システムから分離された軽量コンテナー内で分離します。 信頼されていないサイトまたは PDF ドキュメントが悪意のあると判明した場合でも、デスクトップ PC を保護し、攻撃者をエンタープライズ データから遠く離して、Application Guard のセキュリティで保護されたコンテナーに含まれるままです。|
|[Windows DefenderSystem Guard](/windows/security/threat-protection/windows-defender-system-guard/how-hardware-based-root-of-trust-helps-protect-windows)|System Guard は、システムの開始および実行後にシステムの整合性を保護および維持し、構成証明を使用してシステムの整合性を検証します。|
|
