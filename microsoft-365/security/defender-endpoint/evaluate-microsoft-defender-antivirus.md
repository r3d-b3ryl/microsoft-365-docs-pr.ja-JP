---
title: Microsoft Defender ウイルス対策を評価する
description: すべてのサイズの企業は、このガイドを使用して、ユーザーが提供する保護を評価し、Microsoft Defender ウイルス対策テストWindows 10。
keywords: Microsoft Defender ウイルス対策、クラウド保護、クラウド、マルウェア対策、セキュリティ、防御者、評価、テスト、保護、比較、リアルタイム保護
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 13d3714f1d5843597e19f04a4f94e63f4adf09cb
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192873"
---
# <a name="evaluate-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策を評価する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

このガイドを使用して、ウイルス、マルウェアMicrosoft Defender ウイルス対策望ましくない可能性のあるアプリケーションからユーザーを保護する方法を判断します。

> [!TIP]
>Microsoft Defender for Endpoint のデモ Web サイト demo.wd.microsoft.com、次 [の機能が](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 動作し、動作を確認できます。
>
> - クラウドによる保護
> - 高速学習 (一目でブロックを含む)
> - 望ましくない可能性があるアプリケーションのブロック

小規模企業と大規模企業の両方で利用できる Microsoft Defender ウイルス対策の重要な次世代保護機能と、ネットワーク全体でマルウェアの検出と保護を強化する方法について説明します。

各設定を個別に構成して評価するか、一度にすべて構成するか選択できます。 一般的な評価シナリオに基づいて同様の設定をグループ化し、PowerShell を使用して設定を有効にする手順が含まれています。

このガイドは、オフラインで表示するために PDF 形式で提供されています。

- [ガイドを PDF 形式でダウンロードする](https://www.microsoft.com/download/details.aspx?id=54795)

また、ガイドに記載されている設定を自動的に有効にする PowerShell をダウンロードすることもできます。 上記の PDF ダウンロードと共にスクリプトを取得するか、PowerShell ギャラリーから個別にスクリプトを取得できます。

- [PowerShell スクリプトをダウンロードして、設定を自動的に構成する](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> このガイドは現在、コンピューターの単一コンピューター評価を目的Microsoft Defender ウイルス対策。 このガイドのすべての設定を有効にすると、実際の展開に適していない場合があります。
>
> ネットワーク全体での実際の展開と監視に関する最新の推奨事項については、「deploy Microsoft Defender ウイルス対策」を[参照Microsoft Defender ウイルス対策。](deploy-manage-report-microsoft-defender-antivirus.md)

## <a name="related-topics"></a>関連トピック

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [展開Microsoft Defender ウイルス対策](deploy-manage-report-microsoft-defender-antivirus.md)