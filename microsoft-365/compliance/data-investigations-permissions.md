---
title: データ調査のアクセス許可を割り当てる (プレビュー)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: この記事では、Microsoft 365 でデータ調査ツールを使用するために必要なアクセス許可を設定する方法について説明します。
ms.openlocfilehash: 85a800c3e21c270f46de78bdef77d7b7a98e0eca
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285443"
---
# <a name="assign-permissions-for-data-investigations-preview"></a>データ調査のアクセス許可を割り当てる (プレビュー)

Office 365 または Microsoft 365 コンプライアンスセンターでデータの調査にアクセスするには、データ捜査役割グループのメンバーである必要があります。 役割グループにメンバーを追加するには、組織の管理役割グループのメンバーであるか、セキュリティ & コンプライアンスセンターで役割管理の役割を割り当てられている必要があります。 ユーザーがデータ調査者の役割グループのメンバーになると、メンバーであるデータ調査で調査を作成、アクセス、および実行できるようになります。

データ調査のアクセス許可を割り当てるには

1. に移動 [https://protection.office.com](https://protection.office.com) し、組織内の管理者アカウントの資格情報を使用してサインインします。

2. [セキュリティ & コンプライアンスセンター] で、[ **アクセス許可**] をクリックします。

3. [ **データ** 調査担当者] 役割グループをクリックし、ポップアップページの [ **メンバー** ] の横にある [ **編集**] をクリックします。

4. [ **メンバーの選択** ] をクリックし、[ **追加**] をクリックします。 データ捜査として追加するユーザーを選択し、[ **追加**] をクリックします。

5. すべてのユーザーを追加した後、[ **完了** ] をクリックし、[ **保存** ] をクリックして、役割グループへの変更を保存します。

> [!NOTE]
> データ調査者の役割グループに割り当てられているデータ調査管理役割は、Office 365 または Microsoft 365 コンプライアンスセンターのデータ調査ツールにアクセスするために必要なアクセス許可を提供します。 既定では、この役割は組織の管理役割グループに割り当てられていません。つまり、組織内のグローバル管理者が既定でデータ調査ツールにアクセスできない場合があります。 この問題を解決するには、グローバル管理者をデータ捜査役割グループに追加するか、または "データ調査" 管理役割を "Organization Management/組織の管理" 役割グループに追加します。 3番目のオプションは、カスタム役割グループを作成し、データ調査管理役割 (およびその他の役割) を割り当ててから、適切なメンバーを追加することです。 役割グループと役割の詳細については、「 [セキュリティ & コンプライアンスセンター」の「アクセス許可](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)」を参照してください。
