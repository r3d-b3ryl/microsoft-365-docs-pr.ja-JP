---
title: Enterprise State Roaming を有効にする
description: この記事では、エンタープライズ状態ローミングを有効にする方法について説明します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 65056fc913b88ce0594c9a8b1a89bd2e92b221af
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63326805"
---
# <a name="enable-enterprise-state-roaming"></a>Enterprise State Roaming を有効にする

[エンタープライズ状態ローミングを使用](/azure/active-directory/devices/enterprise-state-roaming-overview) すると、ユーザーとアプリケーションの設定データをクラウドに安全に同期できます。 つまり、サインインする Windows デバイスに関係なく、同じエクスペリエンスが提供されます。 たとえば、Microsoft Managed Desktop デバイスの 1 つを新しいデバイスに置き換える場合、そのデバイスは最後のデバイスとまったく同じように見え、動作します。

エンタープライズ状態ローミングは、ユーザー向けに構成できる Microsoft Managed Desktop サービスのオプション機能です。 Microsoft Managed Desktop の一部として含まれているか、管理されていない。

エンタープライズ状態ローミングを有効にするには、「Azure Active Directory でエンタープライズ状態ローミングを有効にする [」の手順に従います](/azure/active-directory/devices/enterprise-state-roaming-enable)。

>[!NOTE]
>エンタープライズ状態ローミングを有効にした場合、デバイスのセットアップ中に選択された言語が優先言語リストによって上書きされます。 ユーザーはこれを簡単に修正することができますが、最初は一貫性のないローカライズ エクスペリエンスが発生する可能性があります。 デバイスをセットアップする前に、エンタープライズ状態ローミングがユーザーに適切かどうかを確認します。

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft Managed Desktop の使用を開始する手順

1. [管理ポータルで管理者の連絡先を追加および確認する](add-admin-contacts.md)。
2. [条件付きアクセスを調整します](conditional-access.md)。
3. [ライセンスを割り当てる](assign-licenses.md)。
4. [Intune ポータル サイトを展開します](company-portal.md)。
5. エンタープライズ状態ローミングを有効にする (このトピック)。
6. [デバイスを準備します](prepare-devices.md)。
7. [ユーザーがデバイスを使えるようにする](get-started-devices.md)。
8. [アプリを展開する](deploy-apps.md)。
