---
title: 攻撃面の減少の概要
ms.reviewer: ''
description: Microsoft Defender for Endpoint の攻撃表面の縮小機能について説明します。
keywords: asr, 攻撃表面の縮小, Microsoft Defender for Endpoint, microsoft Defender, ウイルス対策, av, Windows Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: asr
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: a736ff05bf729e69f89bdb9050a0c8dec2d033f74101fed7a2f46372872464e0
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53817707"
---
# <a name="overview-of-attack-surface-reduction-capabilities"></a>攻撃表面の縮小機能の概要

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

攻撃表面は、組織がサイバー脅威や攻撃に対して脆弱なすべての場所です。 Defender for Endpoint には、攻撃の表面を減らすのに役立ついくつかの機能が含まれています。 攻撃表面の縮小の詳細については、次のビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4woug]

## <a name="resources-to-learn-more-about-attack-surface-reduction"></a>攻撃表面の縮小について詳しくは、リソースを参照してください。

ビデオで説明したように、Defender for Endpoint には、いくつかの攻撃表面の縮小機能が含まれています。 詳細については、次のリソースを使用します。

| 記事 | 説明 |
|:---|:---|
| [ハードウェア ベースの分離](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview) | システムの開始と実行中のシステムの整合性を保護し、維持します。 ローカル構成証明とリモート構成証明を使用してシステムの整合性を検証します。 悪意のある web サイトからMicrosoft Edgeを保護するために、コンテナーの分離を使用します。 |
| [アプリケーション制御](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) | アプリケーション制御を使用して、アプリケーションを実行するために信頼を得る必要があります。 |
| [制御されたフォルダー アクセス](controlled-folders.md) | 悪意のあるアプリや疑わしいアプリ (ファイル暗号化ランサムウェア マルウェアを含む) がキー システム フォルダー内のファイルに変更を加えるのを防ぐのに役立ちます (Microsoft Defender ウイルス対策) |
| [ネットワーク保護](network-protection.md) | 組織のデバイス上のネットワーク トラフィックと接続に対する保護を拡張します。 (必要なMicrosoft Defender ウイルス対策) |
| [エクスプロイト保護](exploit-protection.md) | 組織が使用するオペレーティング システムとアプリが悪用されるのを保護するのに役立ちます。 エクスプロイト保護は、サードパーティのウイルス対策ソリューションでも機能します。 |
| [攻撃面の減少ルール](attack-surface-reduction.md) | マルウェアの阻止に役立つインテリジェントなルールを使用して、アプリケーションの脆弱性 (攻撃面) を減らします。 (必要なMicrosoft Defender ウイルス対策)。 |
| [デバイス コントロール](device-control-report.md) | 組織内のリムーバブル ストレージや USB ドライブなどのデバイスで使用されるメディアを監視および制御することにより、データ損失から保護します。 |
