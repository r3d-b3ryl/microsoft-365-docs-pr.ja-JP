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
---

# <a name="enable-enterprise-state-roaming"></a>Enterprise State Roaming を有効にする

[Enterprise状態ローミングを使用](/azure/active-directory/devices/enterprise-state-roaming-overview)すると、ユーザーとアプリケーションの設定データをクラウドに安全に同期できます。 つまり、どのデバイスにサインインしても、同Windowsエクスペリエンスが得されます。 たとえば、Microsoft Managed Desktop デバイスの 1 つを新しいデバイスに置き換える場合、そのデバイスは最後のデバイスとまったく同じように見え、動作します。

Enterprise状態ローミングは、ユーザー用に構成できる Microsoft Managed Desktop サービスのオプション機能です。 Microsoft Managed Desktop の一部として含まれているか、管理されていない。

状態ローミングEnterprise有効にするには、「デバイスの状態ローミングを有効にするEnterprise[」の手順に従Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable)。

>[!NOTE]
>[状態ローミングEnterprise有効にした場合、デバイスのセットアップ中に選択した言語が優先言語リストによって上書きされます。 ユーザーはこれを簡単に修正することができますが、最初は一貫性のないローカライズ エクスペリエンスが発生する可能性があります。 デバイスをEnterpriseする前に、ユーザーに適切な状態ローミングが必要かどうかを判断します。

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft Managed Desktop の使用を開始する手順

1. [管理ポータルで管理者の連絡先を追加および確認する](add-admin-contacts.md)。
2. [条件付きアクセスを調整します](conditional-access.md)。
3. [ライセンスを割り当てる](assign-licenses.md)。
4. [展開Intune ポータル サイト](company-portal.md)。
5. 状態Enterpriseを有効にします (このトピック)。
6. [デバイスをセットアップする](set-up-devices.md)。
7. [ユーザーがデバイスを使えるようにする](get-started-devices.md)。
8. [アプリを展開する](deploy-apps.md)。
