---
title: Microsoft Defender ウイルス対策の評価
description: すべてのサイズの企業は、このガイドを使用して、Windows 10 で Microsoft Defender Antivirus が提供する保護を評価およびテストできます。
keywords: Microsoft Defender Antivirus, クラウド保護, クラウド, マルウェア対策, セキュリティ, 防御者, 評価, テスト, 保護, 比較, リアルタイム保護
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7f3fa1ca854a75025f850c85637cd3e08678bdbc
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764833"
---
# <a name="evaluate-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策の評価

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

このガイドを使用して、ウイルス、マルウェア、望ましくない可能性のあるアプリケーションから Microsoft Defender ウイルス対策がどのように保護されるのか確認します。

>[!TIP]
>Microsoft Defender for Endpoint のデモ Web サイト demo.wd.microsoft.com、次 [の機能が](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 動作し、動作を確認できます。
>- クラウドによる保護
>- 高速学習 (一目でブロックを含む)
>- 望ましくない可能性があるアプリケーションのブロック

これは、小規模企業と大企業の両方で利用できる Microsoft Defender Antivirus の重要な次世代保護機能と、ネットワーク全体でマルウェアの検出と保護を強化する方法について説明します。

各設定を個別に構成して評価するか、一度にすべて構成するか選択できます。 一般的な評価シナリオに基づいて同様の設定をグループ化し、PowerShell を使用して設定を有効にする手順が含まれています。

このガイドは、オフラインで表示するために PDF 形式で提供されています。

- [ガイドを PDF 形式でダウンロードする](https://www.microsoft.com/download/details.aspx?id=54795)

また、ガイドに記載されている設定を自動的に有効にする PowerShell をダウンロードすることもできます。 上記の PDF ダウンロードと共にスクリプトを取得するか、PowerShell ギャラリーから個別にスクリプトを取得できます。

- [PowerShell スクリプトをダウンロードして、設定を自動的に構成する](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> このガイドは現在、Microsoft Defender Antivirus の単一コンピューター評価を対象としています。 このガイドのすべての設定を有効にすると、実際の展開に適していない場合があります。
>
> ネットワーク全体での Microsoft Defender ウイルス対策の実際の展開と監視に関する最新の推奨事項については [、「Deploy Microsoft Defender Antivirus」を参照してください](deploy-manage-report-microsoft-defender-antivirus.md)。

## <a name="related-topics"></a>関連項目

- [Windows 10 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender ウイルス対策の展開](deploy-manage-report-microsoft-defender-antivirus.md)