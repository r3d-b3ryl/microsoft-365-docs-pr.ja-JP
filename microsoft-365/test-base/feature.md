---
title: 機能更新プログラムの検証
description: 機能更新プログラムの検証のためにアプリケーションをアップロードする方法の詳細
search.appverid: MET150
author: mansipatel-usl
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: tinachen
f1.keywords: NOCSH
ms.openlocfilehash: 02693d1dc9637b97d6d567a6bc362eaef24adc5d
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2022
ms.locfileid: "67315502"
---
# <a name="windows-feature-update-validation"></a>Windows 機能更新プログラムの検証

新しい Windows 機能を検証する環境を維持せずに、Windows 10またはWindows 11の次のリリースでアプリケーションがどのように実行されるかについての分析情報が必要ですか? 

Azure 環境で Windows Insider Program ビルドに対して検証テストを実行しますか?

M365 の Test Base での **機能更新プログラム** の検証は、これらすべてを達成するのに役立ちます。

M365 サービスの Test Base でこの新しい機能にアクセスする方法については、以下のステップ バイ ステップの概要を参照してください。

Test Base for M365 の使用を開始 ```Feature update validation``` するには、セルフサービスオンボード ポータルを使用してアプリケーション (および関連ファイル) をアップロードします。 

**テストの詳細** を入力するときに実行する手順を次に示します。

1. OS **更新プログラム** の種類として [機能更新プログラム] を選択します。

![機能更新プログラムの検証 OS の種類。](Media/Feature-update-validation-01.png)

2. アプリケーションを検証する Windows Insider チャネルを選択します。  

![機能更新プログラムの検証。 Insider ベータ チャネルの選択。](Media/Feature-update-validation-02.png)

3. テストのベースラインとしてWindows 10またはWindows 11の市場内リリース (および結果の分析情報) を選択し、パッケージを正常にオンボードするために必要なその他の詳細を指定します。

![リリースされたバージョンのWindows 10とWindows 11を使用した機能更新プログラムの検証。](Media/Feature-update-validation-03.png)

4. プレリリースされたWindows 10機能更新プログラムに対するアプリケーションの検証の結果を表示するには、次のページを```Feature Updates Test Results```参照してください。

![機能更新プログラムの検証を使用すると、結果をすばやく確認できます。](Media/Feature-update-validation-04.png)


## <a name="next-steps"></a>次の手順

次の記事に進み、メモリ回帰分析の概要を理解します。
> [!div class="nextstepaction"]
> [次のステップ](memory.md)

<!---
Add button for next page
-->
