---
title: Microsoft のトピックへのアクセスを制限する
description: トピックが検出されるのを防ぐために除外する方法。
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
- m365initiative-topics
localization_priority: None
ms.openlocfilehash: 6b3d2a4b6cbfc67623cea58b73681b7af7cc4889
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107160"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a>Microsoft のトピックへのアクセスを制限する

Microsoft マイクロソフトでは、組織内の関係者は、特定のトピックが検出され、ライセンスされたユーザーに公開されていないことを確認する必要がある場合があります。 たとえば、まだ情報を公開したくないプロジェクトに取り組む場合があります。 サイトOfficeその他のリソースに対する 365 のアクセス許可を使用すると、トピック エクスペリエンスのユーザーはトピック内の機密情報を表示することはできませんが、特定のトピックが検出されるのを防ぐための追加のセーフガードがあります。

ナレッジ管理者はナレッジ ネットワークの設定を制御してトピックが検出されるのを防ぐ一方で、ナレッジ マネージャーや他の関係者は、共同作業を行う方法を知る必要があります。

> [!Important] 
> この記事では、AI を通じてトピックが識別されるのを防ぐ方法、または環境内で追加のセキュリティ保護として表示されるのを防ぐ方法について説明します。 重要な注意点として、ユーザーは、Office 365 のアクセス許可を介してアクセスすることが許可されていないトピック内の何も表示できない点に注意してください。 ユーザーがトピックを表示できる場合でも、表示する Office 365 のアクセス許可を持たなくても、そのユーザーのファイル、サイト、およびページは表示されません。 機密ファイルへのアクセス許可が正しく設定されていることを確認することは、主なセキュリティ保護策である必要があります。

## <a name="prevent-topics-from-being-identified"></a>トピックが特定されるのを防ぐ

ナレッジ管理者は、最初のインデックス作成で特定のトピックが見つからないのを防ぐことで、特定のトピックへのアクセスを制限できます。 このタスクを行うには、Microsoft 365 管理センターのナレッジ ネットワークの管理設定に 2 つの方法があります。
 
- [トピックの検出から](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)除外する SharePoint サイトを選択する : この設定を使用すると、特定の SharePoint サイトがトピックに対してクロールされるのを防ぐのに使用できます。
- [名前でトピックを除外](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name)する : 管理者は、この設定を使用して、特定のトピックが名前で検出されるのを防ぐことが可能です。 サポート技術情報ネットワークの管理者設定では、管理者は CSV ファイルで除外するトピックの一覧をアップロードできます。 トピック名と完全に一致するトピックまたは部分的に一致するトピックを除外できます。

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>特定のユーザーによってトピックが表示されるのを防ぐ

ナレッジ管理者は、組織内 [のトピックを表示できるユーザーを選択することもできます](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)。 この設定では、すべてのトピックを表示できるライセンスユーザーを選択できます。 たとえば、パイロット環境では、小規模なユーザー グループだけがトピックを表示できる場合があります。

## <a name="remove-topics-from-being-viewed"></a>トピックを表示から削除する

ナレッジ マネージャーは、トピック [を削除](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) して、ユーザーに表示されなくなったトピックを削除できます。 トピック センター **の [** トピックの管理] ページで、ナレッジ マネージャーは特定のトピックを拒否して表示を防ぐことを選択できます。 トピックが推奨または確認済み状態の場合に関係なく、トピックを削除できます。

削除されたトピックは、必要に応じて表示可能なトピックとして後で追加できます。 


## <a name="see-also"></a>関連項目



  






