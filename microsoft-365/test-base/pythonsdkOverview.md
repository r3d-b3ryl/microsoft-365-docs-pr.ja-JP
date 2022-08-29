---
title: Python 用の Base SDK をテストする
description: Test Base の Python 用 SDK について理解する方法の詳細
search.appverid: MET150
author: mansipatel-usl
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: article
ms.date: 07/06/2021
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: tinachen
f1.keywords: NOCSH
ms.openlocfilehash: 90a8348e2bde22fa2d0358b9d1696798e089d328
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2022
ms.locfileid: "67316514"
---
# <a name="test-base-sdk-for-python"></a>Python 用の Base SDK をテストする

## <a name="overview"></a>概要
Test Base SDK を使用して、Azure のテスト ベース リソースを操作できます。 (つまり、アプリケーション パッケージを管理し、パッケージの作成、パッケージの編集、パッケージの削除を含めます)。

SDK では、取得できるテストの概要と分析結果には、scriptExecution、信頼性、memoryUtilization、cpuUtilization、memoryRegression、cpuRegression が含まれます。

Test Base SDK を使用すると、CI/CD パイプラインにテスト ベースを統合できます。

## <a name="client-library"></a>クライアント ライブラリ

pip を使用してテスト ベース パッケージをインストールします。

~~~
pip install  Microsoft.Testbase
~~~
 
## <a name="example"></a>例
