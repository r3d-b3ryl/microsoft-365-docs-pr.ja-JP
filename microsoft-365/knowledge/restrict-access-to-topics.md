---
title: トピックへのアクセスを制限する
description: トピックが検出されるのを防ぐために除外する方法。
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: b23d01585d9282132d9e55c74bb22bcdc6ca314a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698962"
---
# <a name="restrict-access-to-topics-in-topic-experiences"></a>トピック エクスペリエンスのトピックへのアクセスを制限する

トピック エクスペリエンスでは、組織内の関係者は、特定のトピックが検出され、ライセンスされたユーザーに公開されていないことを確認する必要があります。 たとえば、まだ情報を公開したくないプロジェクトに取り組む場合があります。 サイトOfficeその他のリソースに対する 365 のアクセス許可を使用すると、トピック エクスペリエンスのユーザーはトピック内の機密情報を表示することはできませんが、特定のトピックが検出されるのを防ぐための追加のセーフガードがあります。

ナレッジ管理者はナレッジ ネットワークの設定を制御してトピックが検出されるのを防ぐ一方で、ナレッジ マネージャーや他の関係者は、この作業を共同で行う方法を知る必要があります。

> [!Important] 
> この記事では、AI を介してトピックが識別されるのを防ぐ方法や、環境内で追加のセキュリティ保護として見なされる方法について説明します。 トピック エクスペリエンスでは、ユーザーは 365 のアクセス許可を介してアクセスできないトピックを何も表示Office重要です。 ユーザーがトピックを表示できる場合でも、表示する Office 365 のアクセス許可を持たなくても、そのユーザーのファイル、サイト、およびページは表示されません。 機密ファイルへのアクセス許可が正しく設定されていることを確認することは、主なセキュリティ保護策である必要があります。

## <a name="prevent-topics-from-being-identified"></a>トピックが特定されるのを防ぐ

ナレッジ管理者は、最初のインデックス作成で特定のトピックが見つからないのを防ぐことで、特定のトピックへのアクセスを制限できます。 これを行うには、Microsoft 365 管理センターのナレッジ ネットワークの管理設定に 2 つの方法があります。
 
- [トピックの検出から](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)除外する SharePoint サイトを選択する : この設定を使用すると、特定の SharePoint サイトがトピックに対してクロールされるのを防ぐのに使用できます。
- [名前でトピックを除外](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name)する : 管理者は、この設定を使用して、特定のトピックが名前で検出されるのを防ぐことが可能です。 サポート技術情報ネットワークの管理者設定では、管理者は CSV ファイルで除外するトピックの一覧をアップロードできます。 トピック名と完全に一致するトピックまたは部分的に一致するトピックを除外できます。

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>特定のユーザーによってトピックが表示されるのを防ぐ

ナレッジ管理者は、組織内 [のトピックを表示できるユーザーを選択することもできます](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)。 この設定では、すべてのトピックを表示できるライセンスユーザーを選択できます。 たとえば、パイロット環境では、小規模なユーザー グループだけがトピックを表示できる場合があります。

## <a name="remove-topics-from-being-viewed"></a>トピックを表示から削除する

ナレッジ マネージャーは、トピック [を削除](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) して、ユーザーに表示されなくなったトピックを削除できます。 トピック センター **の [** トピックの管理] ページで、ナレッジ マネージャーは特定のトピックを拒否して表示を防ぐことを選択できます。 トピックが推奨または確認済み状態の場合に関係なく、トピックを削除できます。

削除されたトピックは、必要に応じて後で表示可能なトピックとして追加できます。 


## <a name="see-also"></a>関連項目



  






