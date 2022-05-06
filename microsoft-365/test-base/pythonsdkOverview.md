---
title: Python 用の Base SDK をテストする
description: Test Base の Python 用 SDK について理解する方法の詳細
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: article
ms.date: 07/06/2021
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 9a4f64afbf02853ccb68098995c0f05baf2c9b01
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211767"
---
# <a name="test-base-sdk-for-python"></a>Python 用の Base SDK をテストする

## <a name="overview"></a>概要
Test Base SDK を使用して、Azure のテスト ベース リソースを操作できます。 (つまり、アプリケーション パッケージの管理、パッケージの作成、パッケージの編集、パッケージの削除など)

SDK では、取得できるテストの概要と分析結果には、scriptExecution、信頼性、memoryUtilization、cpuUtilization、memoryRegression、cpuRegression が含まれます。

Test Base SDK を使用すると、CI/CD パイプラインにテスト ベースを統合できます。

## <a name="client-library"></a>クライアント ライブラリ

pip を使用してテスト ベース パッケージをインストールします。

~~~
pip install  Microsoft.Testbase
~~~
 
## <a name="example"></a>例
