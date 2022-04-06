---
title: 望ましくないソフトウェア
ms.reviewer: ''
description: 望ましくないソフトウェアが同意なしに既定の設定を変更する方法と、自分を保護するために何が可能かについて学ぶ。
keywords: セキュリティ、マルウェア、保護、望ましくない、ソフトウェア、変更、感染、望ましくないソフトウェア、ソフトウェア バンドル、ブラウザー修飾子、プライバシー、セキュリティ、コンピューティング エクスペリエンス、感染防止、ソリューション、WDSI、MMPC、Microsoft マルウェア プロテクション センター、ウイルス調査の脅威、調査マルウェア、PC 保護、コンピューター感染、ウイルス感染、説明、修復、最新の脅威
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
ms.openlocfilehash: 94b3bad5b5653420d91cd422d40a0ff7802e6442
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63683552"
---
# <a name="unwanted-software"></a>望ましくないソフトウェア

望ましくないソフトウェアは、ユーザーの同意や制御Windowsエクスペリエンスを変更するプログラムです。 これは、変更された閲覧エクスペリエンス、ダウンロードとインストールの制御の欠如、誤解を招くメッセージ、またはユーザー設定に対する承認されていない変更Windowsがあります。

## <a name="how-unwanted-software-works"></a>望ましくないソフトウェアのしくみ

ユーザーがインターネットからアプリケーションを検索してダウンロードすると、望ましくないソフトウェアが導入される可能性があります。 一部のアプリケーションはソフトウェア バンドルプログラムで、他のアプリケーションと一緒にパックされます。 その結果、元のアプリケーションのダウンロード時に他のプログラムが誤ってインストールされる可能性があります。

望ましくないソフトウェアの表示を次に示します。

- インストールしなかったプログラムとアンインストールが困難なプログラムがあります

- ブラウザーの機能や設定が変更され、表示や変更ができない

- デバイスの正常性やファイルやプログラムに関するメッセージが過剰に発生する

- 簡単に閉じできない広告があります

一部のインジケーターは、混乱が少なく、望ましくないため、認識が難しくなります。 たとえば、望ましくないソフトウェアは、Web ページを変更して特定の広告を表示したり、閲覧アクティビティを監視したり、ブラウザーの制御を削除したりすることができます。

Microsoft は、広範な評価 [基準を使用](criteria.md) して望ましくないソフトウェアを特定します。

## <a name="how-to-protect-against-unwanted-software"></a>不要なソフトウェアから保護する方法

望ましくないソフトウェアの感染を防ぐため、公式の Web サイトから、またはソフトウェアをダウンロードMicrosoft Store。 サードパーティのサイトからソフトウェアをダウンロードする場合は、ご警戒ください。

インターネット[Microsoft Edge](/microsoft-edge/deploy/index)を参照する場合は、このオプションを使用します。 Microsoft Edge、ブラウザーの設定を変更できるブラウザー修飾子を効果的にブロックする追加の保護が含まれています。 Microsoft Edge [SmartScreen](/microsoft-edge/deploy/index) を使用して不要なソフトウェアをホストしている既知の web サイトWindows Defenderブロックします (Internet Explorer)。

[[Microsoft Defender ウイルス対策](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-in-windows-10)でWindows 10。 脅威に対するリアルタイムの保護を提供し、既知の不要なソフトウェアを検出および削除します。

7 [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201) Vista でリアルタイム保護をWindowsダウンロードWindowsします。

一般的なヒントについては、「マルウェアの [感染を防ぐ」を参照してください](prevent-malware-infection.md)。

### <a name="what-should-i-do-if-my-device-is-infected"></a>デバイスが感染している場合は、どのような操作を行う必要がありますか? 

不要なソフトウェアがある疑いがある場合は、分析のために [ファイルを提出できます](https://www.microsoft.com/wdsi/filesubmission)。

一部の不要なソフトウェアはアンインストール エントリを追加します。つまり、アンインストール エントリを使用して削除 **設定。**
1. [スタート] ボタンを選択する
2. [アプリ] **設定 >アプリ>機能&移動します**。
3. アンインストールするアプリを選択し、[アンインストール] を **クリックします**。

最近、望ましくないソフトウェア感染の症状に気付いた場合は、インストール日別にアプリを並べ替え、インストールしなかった最新のアプリをアンインストールすることを検討してください。

また、ブラウザーでブラウザー **の** アドオン (Internet Explorer、Chrome など) を削除する必要がある場合があります。

脅威の削除が失敗した場合は、マルウェアの [検出と削除の問題のトラブルシューティングに関する記事をご覧ください](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware)。