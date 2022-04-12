---
title: Microsoft Defender ウイルス対策を評価する
description: あらゆる規模の企業は、このガイドを使用して、WindowsのMicrosoft Defender ウイルス対策によって提供される保護を評価およびテストできます。
keywords: Microsoft Defender ウイルス対策、クラウド保護、クラウド、マルウェア対策、セキュリティ、Defender、評価、テスト、保護、比較、リアルタイム保護
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
ms.openlocfilehash: 8c7ced9c85ec7c6075b44970d25e34ba5594404e
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64787637"
---
# <a name="evaluate-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策を評価する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- Microsoft Defender ウイルス対策
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

**プラットフォーム**
- Windows

このガイドを使用して、Microsoft Defender ウイルス対策がウイルス、マルウェア、および望ましくない可能性のあるアプリケーションからユーザーをどの程度適切に保護しているかを判断します。

> [!TIP]
>demo.wd.microsoft.com のMicrosoft Defender for Endpointデモ Web [サイトにアクセス](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)して、次の機能が動作していることを確認し、動作を確認することもできます。
>
> - クラウドによる保護
> - 高速学習 (一目でブロックを含む)
> - 望ましくない可能性があるアプリケーションのブロック

> [!NOTE]
> demo.wd.microsoft.com の Defender for Endpoint デモ サイトは推奨されません。今後削除される予定です。

小規模企業と大企業の両方で利用できるMicrosoft Defender ウイルス対策の重要な次世代保護機能と、ネットワーク全体でマルウェアの検出と保護を強化する方法について説明します。

各設定を個別に構成して評価するか、一度にすべて評価するかを選択できます。 一般的な評価シナリオに基づいて同様の設定をグループ化し、PowerShell を使用して設定を有効にする手順も含まれています。

このガイドは、オフラインで表示するために PDF 形式で入手できます。

- [ガイドを PDF 形式でダウンロードする](https://www.microsoft.com/download/details.aspx?id=54795)

また、ガイドで説明されているすべての設定を自動的に有効にする PowerShell をダウンロードすることもできます。 上記の PDF ダウンロードと共に、またはPowerShell ギャラリーから個別にスクリプトを取得できます。

- [PowerShell スクリプトをダウンロードして設定を自動的に構成する](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> このガイドは現在、Microsoft Defender ウイルス対策の単一マシン評価を目的としています。 このガイドのすべての設定を有効にすることは、実際の展開には適していない可能性があります。
>
> ネットワーク全体でのMicrosoft Defender ウイルス対策の実際の展開と監視に関する最新の推奨事項については、「[Microsoft Defender ウイルス対策のデプロイ」を](deploy-manage-report-microsoft-defender-antivirus.md)参照してください。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS でMicrosoft Defender for Endpointの基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [IntuneのMicrosoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux でMicrosoft Defender for Endpointの基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android の機能で Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能でMicrosoft Defender for Endpointを構成する](ios-configure-features.md)

## <a name="related-topics"></a>関連項目

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender ウイルス対策を展開する](deploy-manage-report-microsoft-defender-antivirus.md)