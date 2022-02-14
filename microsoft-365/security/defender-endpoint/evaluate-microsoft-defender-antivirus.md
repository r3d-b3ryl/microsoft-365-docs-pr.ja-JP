---
title: Microsoft Defender ウイルス対策を評価する
description: すべてのサイズの企業は、このガイドを使用して、ユーザーが提供する保護を評価し、テストMicrosoft Defender ウイルス対策をWindows。
keywords: Microsoft Defender ウイルス対策、クラウド保護、クラウド、マルウェア対策、セキュリティ、防御者、評価、テスト、保護、比較、リアルタイム保護
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 4dd25a599f144a60bfd2ebeb3e9bb8b1876bd3c6
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2022
ms.locfileid: "62807418"
---
# <a name="evaluate-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策を評価する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

このガイドを使用して、ウイルス、マルウェアMicrosoft Defender ウイルス対策望ましくない可能性のあるアプリケーションからユーザーを保護する方法を判断します。

> [!TIP]
>Microsoft Defender for Endpoint のデモ web サイトを demo.wd.microsoft.com、次 [の機能が](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 動作し、その動作を確認できます。
>
> - クラウドによる保護
> - 高速学習 (一目でブロックを含む)
> - 望ましくない可能性があるアプリケーションのブロック

> [!NOTE]
> Defender for Endpoint のデモ サイトは demo.wd.microsoft.com 廃止され、今後削除される予定です。

小規模企業と大規模企業の両方で利用できる Microsoft Defender ウイルス対策の重要な次世代保護機能と、ネットワーク全体でマルウェアの検出と保護を強化する方法について説明します。

各設定を個別に構成して評価するか、一度にすべて構成するか選択できます。 一般的な評価シナリオに基づいて同様の設定をグループ化し、PowerShell を使用して設定を有効にする手順が含まれています。

このガイドは、オフラインで表示するために PDF 形式で提供されています。

- [ガイドを PDF 形式でダウンロードする](https://www.microsoft.com/download/details.aspx?id=54795)

また、ガイドに記載されている設定を自動的に有効にする PowerShell をダウンロードすることもできます。 上記の PDF ダウンロードと共にスクリプトを取得するか、PowerShell ギャラリーから個別にスクリプトを取得できます。

- [PowerShell スクリプトをダウンロードして、設定を自動的に構成する](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> このガイドは現在、コンピューターの単一コンピューター評価を目的Microsoft Defender ウイルス対策。 このガイドのすべての設定を有効にすると、実際の展開に適していない場合があります。
>
> ネットワーク全体での実際の展開と監視に関する最新の推奨事項については、「deploy Microsoft Defender ウイルス対策」を[参照](deploy-manage-report-microsoft-defender-antivirus.md)Microsoft Defender ウイルス対策。

## <a name="related-topics"></a>関連項目

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [展開Microsoft Defender ウイルス対策](deploy-manage-report-microsoft-defender-antivirus.md)