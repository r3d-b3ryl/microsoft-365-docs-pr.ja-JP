---
title: 望ましくないソフトウェア
ms.reviewer: ''
description: 不要なソフトウェアが同意なしに既定の設定を変更する方法と、自分を保護するためにできることについて説明します。
keywords: セキュリティ, マルウェア, 保護, 不要な, ソフトウェア, 変更, 感染, 望ましくないソフトウェア, ソフトウェア バンドル, ブラウザー修飾子, プライバシー, セキュリティ, コンピューティング エクスペリエンス, 感染を防ぐ, ソリューション, WDSI, MMPC, Microsoft マルウェア プロテクション センター, ウイルス研究の脅威, 研究マルウェア, PC 保護, コンピューター感染, ウイルス感染, 説明, 修復, 最新の脅威
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.localizationpriority: medium
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 654730571de934552d983e1135f24a3299567741
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666682"
---
# <a name="unwanted-software"></a>望ましくないソフトウェア

不要なソフトウェアとは、お客様の同意や制御なしにWindowsエクスペリエンスを変更するプログラムです。 これは、変更された閲覧エクスペリエンス、ダウンロードとインストールの制御の欠如、誤解を招くメッセージ、またはWindows設定に対する未承認の変更の形式を取る可能性があります。

## <a name="how-unwanted-software-works"></a>不要なソフトウェアのしくみ

不要なソフトウェアは、ユーザーがインターネットからアプリケーションを検索してダウンロードするときに導入できます。 一部のアプリケーションはソフトウェア バンドルであり、他のアプリケーションでパックされていることを意味します。 その結果、元のアプリケーションがダウンロードされたときに、他のプログラムが誤ってインストールされる可能性があります。

不要なソフトウェアの兆候を次に示します。

- インストールしなかったプログラムがあり、アンインストールが困難な場合があります

- ブラウザーの機能または設定が変更され、それらを表示または変更することはできません

- デバイスの正常性またはファイルとプログラムに関する過剰なメッセージがある

- 簡単に閉じることができない広告がある

一部のインジケーターは、中断が少なく、望ましくないため、認識が困難です。 たとえば、不要なソフトウェアは、Web ページを変更して特定の広告を表示したり、閲覧アクティビティを監視したり、ブラウザーの制御を削除したりできます。

Microsoft では、広範な [評価基準](criteria.md) を使用して、望ましくないソフトウェアを特定します。

## <a name="how-to-protect-against-unwanted-software"></a>不要なソフトウェアから保護する方法

望ましくないソフトウェア感染を防ぐには、公式 Web サイトまたはMicrosoft Storeからのみソフトウェアをダウンロードします。 サードパーティのサイトからソフトウェアをダウンロードすることに注意してください。

インターネット[を](/microsoft-edge/deploy/index)閲覧するときにMicrosoft Edgeを使用します。 Microsoft Edgeには、ブラウザーの設定を変更できるブラウザー修飾子を効果的にブロックする追加の保護が含まれています。 Microsoft Edgeでは、[Windows Defender SmartScreen](/microsoft-edge/deploy/index) (Internet Explorer でも使用) を使用して、不要なソフトウェアをホストしている既知の Web サイトもブロックされます。

[Windows 10でMicrosoft Defender ウイルス対策](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-in-windows-10)を有効にします。 脅威に対するリアルタイムの保護を提供し、既知の不要なソフトウェアを検出して削除します。

[Windows](https://www.microsoft.com/download/details.aspx?id=5201) 7 または Windows Vista でリアルタイム保護のためにMicrosoft Security Essentialsをダウンロードします。

より一般的なヒントについては、「 [マルウェア感染の防止](prevent-malware-infection.md)」を参照してください。

### <a name="what-should-i-do-if-my-device-is-infected"></a>デバイスが感染した場合はどうすればよいですか? 

不要なソフトウェアがあると思われる場合は、 [分析のためにファイルを送信](https://www.microsoft.com/wdsi/filesubmission)できます。

一部の不要なソフトウェアはアンインストール エントリを追加します。つまり、**設定を使用して削除** できます。
1. [スタート] ボタンを選択する
2. **[設定 > アプリ>アプリ&機能]** に移動します。
3. アンインストールするアプリを選択し、[ **アンインストール**] をクリックします。

最近、望ましくないソフトウェア感染の症状に気付いた場合は、インストール日別にアプリを並べ替えてから、インストールしなかった最新のアプリをアンインストールすることを検討してください。

また、Internet Explorer、Firefox、Chrome などのブラウザーでブラウザー **アドオンを削除** する必要がある場合もあります。

脅威の削除が失敗した場合は、 [マルウェアの検出と削除に関する問題のトラブルシューティングに関する記事を](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware)参照してください。