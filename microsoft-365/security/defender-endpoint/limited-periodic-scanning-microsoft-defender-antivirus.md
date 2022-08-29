---
title: 制限付き定期的な Microsoft Defender ウイルス対策スキャン機能を有効にする
description: 定期的なスキャンが制限されている場合は、インストールされている他の AV プロバイダーに加えて Microsoft Defender ウイルス対策を使用できます
keywords: lps, limited, periodic, scaning, scanning, compatibility, 3rd party, Other av, disable
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 6c38f5544356bc92493e04651fff9c140888e386
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67385057"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策で限定された定期的なスキャンを使用する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

限られた定期的なスキャンは、Windows 10またはWindows 11デバイスに別のウイルス対策製品をインストールしたときに有効にできる、特別な種類の脅威の検出と修復です。

特定の状況でのみ有効にできます。 限られた定期的なスキャンと、Microsoft Defender ウイルス対策が他のウイルス対策製品とどのように連携するかの詳細については、 [Microsoft Defender ウイルス対策の互換性](microsoft-defender-antivirus-compatibility.md)に関するページを参照してください。

**Microsoft では、エンタープライズ環境でこの機能を使用することはお勧めしません。これは主にコンシューマー向けの機能です。** この機能では、Microsoft Defender ウイルス対策機能の一部のみを使用してマルウェアを検出し、ほとんどのマルウェアや望ましくない可能性のあるソフトウェアを検出することはできません。 また、管理機能とレポート機能は制限されます。 Microsoft では、企業がプライマリウイルス対策ソリューションを選択し、排他的に使用することをお勧めします。

## <a name="how-to-enable-limited-periodic-scanning"></a>限られた定期的なスキャンを有効にする方法

既定では、他のウイルス対策製品がインストールされていない場合、または他の製品が古い場合、期限切れになっている場合、または正しく動作していない場合、Microsoft Defender ウイルス対策は、Windows 10またはWindows 11 デバイスでそれ自体を有効にします。

Microsoft Defender ウイルス対策が有効になっている場合、通常のオプションはそのデバイスで構成するように表示されます。

:::image type="content" source="images/vtp-wdav.png" alt-text="スキャン オプション、設定、更新オプションなど、Microsoft Defender ウイルス対策オプションを示すWindows セキュリティ アプリ" lightbox="images/vtp-wdav.png":::

別のウイルス対策製品がインストールされ、正しく動作している場合、Microsoft Defender ウイルス対策によってそれ自体が無効になります。 Windows セキュリティ アプリは、[**ウイルス&脅威の保護**] セクションを変更して AV 製品に関する状態を表示し、製品の構成オプションへのリンクを提供します。

サード パーティ製の AV 製品の下に、 **Microsoft Defender ウイルス対策オプション** として新しいリンクが表示されます。 このリンクをクリックすると、制限付き定期的なスキャンを有効にするトグルが表示されます。 制限付き定期的なオプションは、定期的なスキャンを有効または無効にするトグルであることに注意してください。 

スイッチを **[オン]** にスライドすると、サード パーティ製の AV 製品の下に標準の Microsoft Defender ウイルス対策オプションが表示されます。 限られた定期的なスキャン オプションがページの下部に表示されます。

## <a name="related-articles"></a>関連記事

- [行動、ヒューリスティック、リアルタイム保護を構成する](configure-protection-features-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)