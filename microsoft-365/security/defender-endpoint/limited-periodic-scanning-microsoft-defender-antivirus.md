---
title: 制限された定期的な Microsoft Defender ウイルス対策スキャン機能を有効にする
description: 定期的なスキャンが制限されている場合は、インストールされている他の AV プロバイダーに加えて Microsoft Defender ウイルス対策を使用できます。
keywords: lps、制限付き、定期的、スキャン、スキャン、互換性、サードパーティ、その他の AV、無効化
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: b2ae56c0f67501eb8603d5d28c4ed0c4af01a8c9
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274598"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策で限定された定期的なスキャンを使用する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

限定的な定期的なスキャンは、Windows 10 デバイスに別のウイルス対策製品をインストールした場合に有効にできる特別な種類の脅威の検出と修復です。

特定の状況でのみ有効にできます。 限定的な定期的なスキャンの詳細と、Microsoft Defender Antivirus が他のウイルス対策製品とどのように動作するのかについては、「Microsoft Defender Antivirus の互換性」 [を参照してください](microsoft-defender-antivirus-compatibility.md)。

**Microsoft では、この機能をエンタープライズ環境で使用することをお勧めしません。これは主にコンシューマー向け機能です。** この機能では、Microsoft Defender Antivirus 機能の限られたサブセットのみを使用してマルウェアを検出し、ほとんどのマルウェアや望ましくない可能性のあるソフトウェアを検出することは可能ではありません。 また、管理およびレポート機能は制限されます。 Microsoft では、企業がプライマリ ウイルス対策ソリューションを選択し、排他的に使用する方法をお勧めします。

## <a name="how-to-enable-limited-periodic-scanning"></a>制限付き定期的なスキャンを有効にする方法

既定では、他のウイルス対策製品がインストールされていない場合、または他の製品が期限切れ、期限切れ、または正しく動作していない場合、Microsoft Defender Antivirus は Windows 10 デバイス上で自身を有効にします。

Microsoft Defender Antivirus が有効になっている場合、通常のオプションが表示され、そのデバイスで構成されます。

![スキャン オプション、設定、更新オプションなど、Microsoft Defender AV オプションを表示する Windows セキュリティ アプリ](images/vtp-wdav.png)

別のウイルス対策製品がインストールされ、正しく動作している場合、Microsoft Defender Antivirus はそれ自体を無効にします。 Windows セキュリティ アプリは、[ウイルス対策&] セクションを変更して、AV 製品に関する状態を表示し、製品の構成オプションへのリンクを提供します。

サードパーティの AV 製品の下に、Microsoft Defender ウイルス対策オプションとして新しい **リンクが表示されます**。 このリンクをクリックすると、制限付き定期的なスキャンを有効にするトグルが表示されます。 制限された定期的なオプションは、定期的なスキャンを有効または無効にするトグルです。 

スイッチを On に **スライドすると** 、サードパーティの AV 製品の下に標準の Microsoft Defender AV オプションが表示されます。 制限された定期的なスキャン オプションがページの下部に表示されます。

## <a name="related-articles"></a>関連記事

- [行動、ヒューリスティック、リアルタイム保護を構成する](configure-protection-features-microsoft-defender-antivirus.md)
- [Windows 10 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)