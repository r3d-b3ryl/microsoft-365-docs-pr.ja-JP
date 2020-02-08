---
title: Project Server の GDPR
description: オンプレミスの Project Server で GDPR の要件に対応する方法について説明します。
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.openlocfilehash: a9fff9f085fd42f28801a82c3f83d6bdd1f74ff6
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596414"
---
# <a name="gdpr-for-project-server"></a>Project Server の GDPR

Project Server では、Project Web App でユーザー データをエクスポートしたり編集したりするために、カスタム スクリプトが使用されます。基本的な処理は、次のとおりです。

1.  ファーム内で Project Web App のサイトを検索します。

2.  各サイトの中で、ユーザーが含まれているプロジェクトを検索します。

3.  確認対象となるタイプのデータをエクスポートし、確認します。

4.  必要に応じてデータを編集します。

これらの手順について、以下の記事で詳細に説明します。

- [Project Server からユーザー データをエクスポートする](/Project/export-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)

- [Project Server からユーザー データを削除する](/Project/delete-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)


Project Server は SharePoint Server 上に構築されており、SharePoint ULS のログおよび利用状況データベースにイベントのログが出力されることに注意してください。詳細は「[SharePoint Server での GDPR への対応](gdpr-for-sharepoint-server.md)」をご覧ください。
