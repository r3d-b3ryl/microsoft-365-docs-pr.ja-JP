---
title: テーマ - 電子情報開示
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 各ドキュメントで主なAdvanced eDiscoveryを見つけることで、レビュー セットを整理するには、ページの [テーマ] を使用します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216333"
---
# <a name="themes-in-advanced-ediscovery"></a>[テーマ] Advanced eDiscovery

ユーザーがドキュメントを作成する方法 通常、ドキュメントで伝えたい 1 つ以上のアイデアから始め、アイデアに合った単語を使用して作成します。 一般的なアイデアは、そのアイデアに関連する単語の頻度が高くなる傾向があります。 これにより、ユーザーがドキュメントを使用する方法も通知されます。 ドキュメントを読んで理解する重要な点は、ドキュメントが伝えようとしているアイデア、どこに表示されるアイデア、アイデア間の関係を理解する必要があります。

これは、ユーザーが一連のドキュメントを使用する方法まで拡張できます。 セットにどのアイデアが存在し、どのドキュメントがそれらのアイデアについて話しているのか確認する必要があります。 また、関心のある特定のドキュメントを見つけた場合は、同様のアイデアを議論するドキュメントを見る必要があります。

Advanced eDiscovery のテーマ機能は、レビュー セットで説明されているテーマを分析し、レビュー セット内のドキュメントにテーマを割り当て、ドキュメントに関する人間の理由を模倣します。 このAdvanced eDiscoveryテーマはさらに一歩進み、各ドキュメントの主要 *なテーマ* を識別します。 主なテーマは、ドキュメント内で最も頻繁に表示されるテーマです。

## <a name="how-does-themes-work"></a>テーマの動作

テーマ機能は、レビューセット内のテキストを含むドキュメントを分析して、レビューセット内のすべてのドキュメントにわたって表示される共通のテーマを解析します。 Advanced eDiscovery は、テーマを、それらが表示されるドキュメントに割り当てます。 また、テーマには、テーマを表すドキュメントで使用されている単語を各テーマにラベル付けします。 ドキュメントにはさまざまな種類の主題が含まれる可能性があるため、Advanced eDiscovery は複数のテーマをドキュメントに割り当てることがよくあります。 ドキュメントで最も目立つテーマは、その主要なテーマとして指定されます。
