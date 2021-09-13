---
title: サイト内のトピックへのアクセスを制限Microsoft Viva トピック
description: トピックが検出されるのを防ぐためにトピックを除外する方法。
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: d6dfb2f7f432a40c5b6e96a9437f50ba47e23387
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59179567"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a>サイト内のトピックへのアクセスを制限Microsoft Viva トピック

このMicrosoft Viva、組織内の関係者は、特定のトピックが検出され、ライセンスを受け取ったユーザーに公開されていないことを確認する必要があります。 たとえば、まだ情報を公開しないプロジェクトに取り組む場合があります。 サイトOffice 365、ファイル、その他のリソースに対するアクセス許可を使用すると、Topic Experiences ユーザーはトピック内の機密情報を表示することはできませんが、特定のトピックが検出されるのを防ぐための追加のセーフガードがあります。

ナレッジ管理者が設定を制御してトピックが検出されるのを防ぐ一方で、ナレッジ マネージャーや他の利害関係者は、作業を共同で行う方法を知る必要があります。

> [!Important] 
> この記事では、トピックが AI を介して識別されるのを防ぐ方法、または環境内で追加のセキュリティ保護手段として表示する方法について説明します。 ビバ トピックでは、ユーザーがトピック内のアクセス許可を使用してアクセスできない内容を表示することは許可Office 365です。 ユーザーがトピックを表示できる場合でも、そのユーザーのファイル、サイト、およびページには、Office 365アクセス許可が付与されていないと、ユーザーは表示されません。 機密性の高いファイルに対するアクセス許可が正しく設定されていることを確認することは、主なセキュリティ保護策である必要があります。

## <a name="prevent-topics-from-being-identified"></a>トピックが識別されるのを防ぐ

ナレッジ管理者は、最初のインデックス作成で特定のトピックが見つからないのを防ぐことで、特定のトピックへのアクセスを制限できます。 このタスクを実行するには、次の 2 つの方法が[ビバ トピック] 管理設定Microsoft 365 管理センター。
 
- [トピックSharePoint除外](./topic-experiences-discovery.md#select-sharepoint-topic-sources)するサイトを選択します。この設定を使用すると、特定のサイトがトピックSharePointクロールされるのを防ぐことが可能です。
- [名前でトピックを除外する](./topic-experiences-discovery.md#exclude-topics-by-name): 管理者は、この設定を使用して、特定のトピックが名前で検出されるのを防ぐ場合があります。 ビバ トピックの管理設定では、管理者は CSV ファイルで除外するトピックの一覧をアップロードできます。 トピック名に完全一致または部分的に一致するトピックを除外できます。

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>トピックが特定のユーザーによって表示されるのを防ぐ

ナレッジ管理者は、組織内 [のトピックを表示できるユーザーを選択することもできます](./topic-experiences-knowledge-rules.md)。 この設定では、すべてのトピックを表示できるライセンスユーザーを選択できます。 たとえば、パイロット環境では、小さなグループのユーザーだけがトピックを表示できる場合があります。

## <a name="remove-topics-from-being-viewed"></a>トピックを表示から削除する

ナレッジ マネージャーは、ユーザー [がトピックを表示](./manage-topics.md) できなくなった場合に、トピックを削除できます。 トピック センター **の [トピックの** 管理] ページで、ナレッジ マネージャーは特定のトピックを拒否して表示を防止できます。  トピックは、提案または確認済み状態の場合に関係なく削除できます。

削除されたトピックは、必要に応じて表示可能なトピックとして後で追加できます。 


## <a name="see-also"></a>関連項目



