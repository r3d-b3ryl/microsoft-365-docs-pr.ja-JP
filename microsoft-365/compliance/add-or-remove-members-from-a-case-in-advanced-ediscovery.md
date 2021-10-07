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
ms.openlocfilehash: 13a97af715a3f81b5570617f18b10cd8e35f9aec
ms.sourcegitcommit: afee35210f8d68a7f20676ff2a829464b0b0adb2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2021
ms.locfileid: "60217104"
---
# <a name="add-or-remove-members-from-a-case"></a>ケースからメンバーを追加または削除する

メンバーを追加または削除して、ケースにアクセスできるユーザーを管理できます。 ただし、メンバーが Advanced eDiscovery ケースにアクセスし (この場合はタスクを実行する) 前に、Microsoft 365 コンプライアンス センター の [アクセス許可] ページの電子情報開示マネージャー役割グループにユーザーを追加する必要があります。 詳細については、「[電子情報開示のアクセス許可を割り当てる](./assign-ediscovery-permissions.md)」を参照してください。電子情報開示のアクセス許可を割り当てる」を参照してください。

1. **Advanced eDiscovery** ページで、メンバーを追加するケースに移動します。

2. [**設定**] タブをクリックし、[**アクセス & アクセス許可**] タイルで [**選択**] をクリックします。

3. **[更新]** をクリックします。

4. [**メンバーの管理**] で [**追加**] をクリックして、ケースにメンバーを追加します。 [役割グループの管理] で [追加] をクリックして、役割グループをケース **に追加することもできます**。

5. ケースのメンバーとして追加できるユーザーまたは役割グループのリストで、追加するユーザーまたは役割グループの名前の横にあるチェック ボックスをオンにします。

   > [!NOTE]
   > 役割グループをケースに追加する場合は、自分がメンバーである役割グループのみを追加できます。

6. ケースのメンバーとして追加するユーザーまたは役割グループを選択した後、[追加] を **クリックします**。

7. [**このケースを管理**] で、[**保存**] をクリックして、ケース メンバーの新しいリストを保存します。

> [!IMPORTANT]
> ケースのメンバーとして追加した役割グループから役割が追加または削除された場合、その役割グループはケースのメンバー (または役割グループがメンバーである場合) として自動的に削除されます。 その理由は、ケースのメンバーに不注意で追加のアクセス許可を与えてしまうのを組織が保護する理由です。 同様に、役割グループが削除された場合は、そのグループがメンバーだったすべてのケースから削除されます。 詳細については、「[電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md#adding-role-groups-as-members-of-ediscovery-cases)」を参照してください。電子情報開示のアクセス許可を割り当てる」を参照してください。
