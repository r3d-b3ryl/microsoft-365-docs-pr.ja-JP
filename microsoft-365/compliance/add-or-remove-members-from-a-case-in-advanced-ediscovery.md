---
title: ケースからメンバーを追加または削除する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ケースを管理するときにケースにアクセスできるメンバーを追加または削除する方法Advanced eDiscoveryします。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8e239622add6965a280e9c2b01bc00d9f2b9b0d5
ms.sourcegitcommit: 317fab13e84b2867087a6ba0a593313ecf43bbed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2021
ms.locfileid: "60364665"
---
# <a name="add-or-remove-members-from-a-case"></a>ケースからメンバーを追加または削除する

メンバーを追加または削除して、ケースにアクセスできるユーザーを管理できます。 ただし、メンバーが Advanced eDiscovery ケースにアクセスし (この場合はタスクを実行する) 前に、Microsoft 365 コンプライアンス センター の [アクセス許可] ページの電子情報開示マネージャー役割グループにユーザーを追加する必要があります。 詳細については、「[電子情報開示のアクセス許可を割り当てる](./assign-ediscovery-permissions.md)」を参照してください。電子情報開示のアクセス許可を割り当てる」を参照してください。

1. **Advanced eDiscovery** ページで、メンバーを追加するケースに移動します。

2. [**設定**] タブをクリックし、[**アクセス & アクセス許可**] タイルで [**選択**] をクリックします。

3. [**メンバーの管理**] で [**追加**] をクリックして、ケースにメンバーを追加します。 [役割グループの管理] で [追加] をクリックして、役割グループをケース **に追加することもできます**。

4. ケースのメンバーとして追加できるユーザーまたは役割グループのリストで、追加するユーザーまたは役割グループの名前の横にあるチェック ボックスをオンにします。

   > [!NOTE]
   > 役割グループをケースに追加する場合は、自分がメンバーである役割グループのみを追加できます。

5. ケースのメンバーとして追加するユーザーまたは役割グループを選択した後、[追加] を **クリックします**。

6. [**このケースを管理**] で、[**保存**] をクリックして、ケース メンバーの新しいリストを保存します。

> [!IMPORTANT]
> ケースのメンバーとして追加した役割グループから役割が追加または削除された場合、その役割グループはケースのメンバー (または役割グループがメンバーである場合) として自動的に削除されます。 その理由は、ケースのメンバーに不注意で追加のアクセス許可を与えてしまうのを組織が保護する理由です。 同様に、役割グループが削除された場合は、そのグループがメンバーだったすべてのケースから削除されます。 詳細については、「[電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md#adding-role-groups-as-members-of-ediscovery-cases)」を参照してください。電子情報開示のアクセス許可を割り当てる」を参照してください。

## <a name="removing-members-from-a-case"></a>ケースからメンバーを削除する

ケースから [メンバーを](assign-ediscovery-permissions.md) 削除できるのは、電子情報開示管理者のみです。 電子情報開示マネージャーの役割グループに割り当てられている場合や、ケースを最初に作成した場合でも、電子情報開示管理者でなくても、ケースから自分自身や他のメンバーを削除することはできません。 自分または他のメンバーをケースから削除するには、組織内の電子情報開示管理者に問い合わせてください。
