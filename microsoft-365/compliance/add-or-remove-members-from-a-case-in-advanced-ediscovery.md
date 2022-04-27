---
title: ケースからメンバーを追加または削除する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
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
description: 電子情報開示 (プレミアム) ケースを管理するときにケースにアクセスできるメンバーを追加または削除する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 85a8673e7e3c31ab12cda0109f6c06762adeabf3
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65091877"
---
# <a name="add-or-remove-members-from-a-case"></a>ケースからメンバーを追加または削除する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

メンバーを追加または削除して、ケースにアクセスできるユーザーを管理できます。 ただし、メンバーが電子情報開示 (プレミアム) ケースにアクセスし、ケース内のタスクを実行する前に、Microsoft Purview コンプライアンス ポータルの **[アクセス許可**] ページで電子情報開示マネージャーの役割グループにユーザーを追加する必要があります。 詳細については、「[電子情報開示のアクセス許可を割り当てる](./assign-ediscovery-permissions.md)」を参照してください。電子情報開示のアクセス許可を割り当てる」を参照してください。

1. **[電子情報開示 (プレミアム)]** ページで、メンバーを追加するケースに移動します。

2. [**設定**] タブをクリックし、[**アクセス & アクセス許可**] タイルで [**選択**] をクリックします。

3. [**メンバーの管理**] で [**追加**] をクリックして、ケースにメンバーを追加します。 [役割グループの管理] で [追加] をクリックして、ケースに **役割グループ** を **追加** することもできます。

4. ケースのメンバーとして追加できるユーザーまたは役割グループのリストで、追加するユーザーまたは役割グループの名前の横にあるチェック ボックスをオンにします。

   > [!NOTE]
   > ケースに役割グループを追加する場合は、自分がメンバーである役割グループのみを追加できます。

5. ケースのメンバーとして追加するユーザーまたは役割グループを選択したら、[ **追加**] をクリックします。

6. [**このケースを管理**] で、[**保存**] をクリックして、ケース メンバーの新しいリストを保存します。

> [!IMPORTANT]
> ケースのメンバーとして追加した役割グループにロールが追加または削除された場合、ロール グループはケースのメンバー (またはロール グループがメンバーである場合) として自動的に削除されます。 その理由は、ケースのメンバーに追加のアクセス許可を誤って提供しないように組織を保護するためです。 同様に、役割グループが削除された場合は、そのロール グループがメンバーであったすべてのケースから削除されます。 詳細については、「[電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md#adding-role-groups-as-members-of-ediscovery-cases)」を参照してください。電子情報開示のアクセス許可を割り当てる」を参照してください。

## <a name="removing-members-from-a-case"></a>ケースからメンバーを削除する

ケースからメンバーを削除できるのは [、電子情報開示管理者](assign-ediscovery-permissions.md) のみです。 電子情報開示マネージャーの役割グループに割り当てられている場合、またはケースを最初に作成した場合でも、電子情報開示管理者でない限り、自分または他のメンバーをケースから削除することはできません。 自分や他のメンバーをケースから削除するには、組織内の電子情報開示管理者に問い合わせてください。
