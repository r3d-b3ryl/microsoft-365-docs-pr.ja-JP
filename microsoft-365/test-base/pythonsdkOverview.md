---
title: Python の基本 SDK のテスト
description: テスト ベースの SDK for Python の理解に関する詳細
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: article
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: c7f2d4b7b600e84b2ed35cce320dcb7d7191ecfc
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323127"
---
# <a name="test-base-sdk-for-python"></a>Python の基本 SDK のテスト

## <a name="overview"></a>概要
Test Base SDK を使用して、Azure テスト ベース リソースを操作できます。 (つまり、アプリケーション パッケージの管理、パッケージの作成、パッケージの編集、パッケージの削除を含む)

SDK では、取得できるテストの概要と分析結果が含まれます。scriptExecution、信頼性、memoryUtilization、cpuUtilization、memoryRegression、cpuRegression。

テストベース SDK を使用すると、CI/CD パイプラインにテスト ベースを統合できます。

## <a name="client-library"></a>クライアント ライブラリ

ピップを使用してテストベース パッケージをインストールします。

~~~
pip install  Microsoft.Testbase
~~~
 
## <a name="example"></a>例
