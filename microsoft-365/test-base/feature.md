---
title: 機能更新プログラムの検証
description: 機能更新プログラムの検証のためにアプリケーションをアップロードする方法の詳細
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: f6e7cfffb92f64d92a4ad68d93d1d51dccc0f4bb
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60206387"
---
# <a name="windows-feature-update-validation"></a>Windows機能更新プログラムの検証

Windows 10 または Windows 11 の次のリリースでアプリケーションがどのように実行されるのか、新しい機能を検証するための環境を維持せずに、Windows 必要ですか? 

Azure 環境で Insider Program Windowsに対して検証テストを実行しますか?

 M365 のテスト ベースの機能更新プログラムの検証は、これらすべての機能を実現するのに役立ちます。

以下の手順の概要を参照して、M365 サービスの Test Base でこの新しい機能にアクセスする方法について説明します。

M365 のテスト ベースで始めるには、セルフサービス オンボーディング ポータルを使用してアプリケーション (および関連ファイル ```Feature update validation``` ) をアップロードします。 

以下に、テストの詳細を入力する手順を **示します**。

1. OS **更新プログラムの種類として** [機能更新プログラム] を選択します。

![機能更新プログラムの検証 OS の種類。](Media/Feature-update-validation-01.png)

2. アプリケーションをWindowsする Insider チャネルを選択します。  

![機能更新プログラムの検証。 Insider ベータ チャネルの選択。](Media/Feature-update-validation-02.png)

3. テストのベースラインとして Windows 10 または Windows 11 の市場リリースを選択し (結果として得られる分析情報!)、パッケージの正常なオンボードに必要なその他の詳細を提供します。

![リリースされたバージョンの 11 のバージョンのWindows 10更新Windows検証。](Media/Feature-update-validation-03.png)

4. 事前にリリースされた機能更新プログラムに対するアプリケーションの検証の結果を表示するには、Windows 10を参照してください ```Feature Updates Test Results``` 。

![機能更新プログラムの検証を使用すると、結果をすばやく確認できます。](Media/Feature-update-validation-04.png)


## <a name="next-steps"></a>次の手順

次の記事に進み、メモリ回帰分析について説明します。
> [!div class="nextstepaction"]
> [次の手順](memory.md)

<!---
Add button for next page
-->
