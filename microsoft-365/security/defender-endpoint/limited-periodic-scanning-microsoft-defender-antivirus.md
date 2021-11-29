---
title: 制限された定期的なスキャン機能Microsoft Defender ウイルス対策有効にする
description: 定期的なスキャンが制限されている場合は、インストールMicrosoft Defender ウイルス対策 AV プロバイダーに加えて、定期的なスキャンを使用できます。
keywords: lps、制限付き、定期的、スキャン、スキャン、互換性、サードパーティ、その他の AV、無効化
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
ms.openlocfilehash: e0a8293709da44dc3a46cf565ad099666e8dae24
ms.sourcegitcommit: dfa9f28a5a5055a9530ec82c7f594808bf28d0dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/29/2021
ms.locfileid: "61217455"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策で限定された定期的なスキャンを使用する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

限定的な定期的なスキャンは、Windows 10 Windows または 11 デバイスに別のウイルス対策製品をインストールした場合に有効にできる特別な種類の脅威の検出と修復です。

特定の状況でのみ有効にできます。 制限付き定期的なスキャンと他のウイルス対策Microsoft Defender ウイルス対策の動作の詳細については、「Microsoft Defender ウイルス対策[を参照してください](microsoft-defender-antivirus-compatibility.md)。

**Microsoft では、この機能をエンタープライズ環境で使用することをお勧めしません。これは主にコンシューマー向け機能です。** この機能は、マルウェアを検出するためにMicrosoft Defender ウイルス対策機能の限られたサブセットのみを使用し、ほとんどのマルウェアや望ましくない可能性のあるソフトウェアを検出することは可能ではありません。 また、管理およびレポート機能は制限されます。 Microsoft では、企業がプライマリ ウイルス対策ソリューションを選択し、排他的に使用する方法をお勧めします。

## <a name="how-to-enable-limited-periodic-scanning"></a>制限付き定期的なスキャンを有効にする方法

既定では、Microsoft Defender ウイルス対策 は、他のウイルス対策製品がインストールされていない場合、または他の製品が古い、期限切れになっている、または正しく動作していない場合、Windows 10 または Windows 11 デバイスでそれ自体を有効にします。

有効Microsoft Defender ウイルス対策場合、通常のオプションが表示され、そのデバイスで構成されます。

![Windows セキュリティオプション、設定、更新オプションなど、Microsoft Defender AV オプションを表示するアプリです。](images/vtp-wdav.png)

別のウイルス対策製品がインストールされ、正しく動作している場合、Microsoft Defender ウイルス対策が無効になります。 アプリWindows セキュリティ[ウイルス対策&] セクションが変更され、AV 製品に関する状態が表示され、製品の構成オプションへのリンクが提供されます。

サード パーティの AV 製品の下に、新しいリンクが新しいオプション **としてMicrosoft Defender ウイルス対策されます**。 このリンクをクリックすると、制限付き定期的なスキャンを有効にするトグルが表示されます。 制限された定期的なオプションは、定期的なスキャンを有効または無効にするトグルです。 

スイッチを On に **スライドすると** 、サードパーティの AV 製品の下に標準の Microsoft Defender AV オプションが表示されます。 制限された定期的なスキャン オプションがページの下部に表示されます。

## <a name="related-articles"></a>関連記事

- [行動、ヒューリスティック、リアルタイム保護を構成する](configure-protection-features-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)