---
title: デバイス保護ポリシーの表示または編集
description: デバイス保護ポリシーの表示、編集、作成、およびMicrosoft 365 Business Premium
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/08/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 95bce75fdee629a40907afda04999c6abf1c0e5b
ms.sourcegitcommit: a9266e4e7470e8c1e8afd31fef8d266f7849d781
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2022
ms.locfileid: "63406567"
---
# <a name="view-and-edit-your-device-protection-policies"></a>デバイス保護ポリシーの表示と編集

このMicrosoft 365 Business Premium、管理対象デバイスのセキュリティ設定はデバイス保護ポリシーによって構成されます。 セットアップと構成のエクスペリエンスを簡素化するために、事前に構成されたポリシーを使用して、オンボード後すぐに組織のデバイスを保護できます。 既定のポリシーを使用したり、ポリシーを編集したり、独自のポリシーを作成することができます。

**この記事では、次の方法について説明します**。

- 既定のポリシーの概要を取得する
- 既存のポリシーを表示する
- 既存のポリシーを編集する
- 新しいポリシーの作成

## <a name="default-device-protection-policies"></a>既定のデバイス保護ポリシー

Microsoft 365 Business Premiumのデバイスを保護するための 2 つの主な種類のポリシーが含まれています。

- **次世代の保護ポリシー。** このポリシーは、Microsoft Defender ウイルス対策脅威保護機能の構成方法を決定します。

- **ファイアウォール ポリシー:** 組織のデバイスに対するネットワーク トラフィックの流れと、組織のデバイスからのフローを決定する

これらのポリシーは Microsoft Defender for Business の一部で、このポリシーはサブスクリプションにMicrosoft 365 Business Premiumされます。

## <a name="view-your-existing-device-protection-policies"></a>既存のデバイス保護ポリシーを表示する

1. ポータル () にMicrosoft 365 Defenderし[https://security.microsoft.com](https://security.microsoft.com)、サインインします。 

2. ナビゲーション ウィンドウで、[デバイス構成] **を選択します**。 ポリシーは、オペレーティング システム (Windows **クライアントなど)** とポリシーの種類 (次世代保護やファイアウォールなど) **によって** 編成 **されます**。 

3. [オペレーティング システム] タブ (Windows クライアントなど) **を** 選択し、[次世代の保護] カテゴリと [ファイアウォール] カテゴリの下のポリシーの一覧を **確認** します。 

4. ポリシーの詳細を表示するには、その名前を選択します。 サイド ウィンドウが開き、そのポリシーに関する詳細 (そのポリシーで保護されているデバイスなど) が表示されます。

## <a name="edit-an-existing-device-protection-policy"></a>既存のデバイス保護ポリシーの編集

1. ポータル () にMicrosoft 365 Defenderし[https://security.microsoft.com](https://security.microsoft.com)、サインインします。 

2. ナビゲーション ウィンドウで、[デバイス構成] **を選択します**。 ポリシーは、オペレーティング システム (Windows **クライアントなど)** とポリシーの種類 (次世代保護やファイアウォールなど) **によって** 編成 **されます**。 

3. [オペレーティング システム] タブ (Windows クライアントなど) **を** 選択し、[次世代の保護] カテゴリと [ファイアウォール] カテゴリの下のポリシーの一覧を **確認** します。 

4. ポリシーを編集するには、ポリシーの名前を選択し、[編集] を選択 **します**。

5. [全般情報 **] タブで** 、情報を確認します。 必要に応じて、説明を編集できます。 **[次へ]** を選択します。

6. [デバイス グループ **] タブで** 、このポリシーを受け取るデバイス グループを決定します。  

   - 選択したデバイス グループを保持するには、[次へ] を選択 **します**。
   - ポリシーからデバイス グループを削除するには、[削除] を **選択します**。
   - 新しいデバイス グループを設定するには、[新しいグループの作成] を **選択** し、デバイス グループを設定します。 (このタスクのヘルプを表示するには、「[デバイス](m365bp-device-groups-mdb.md) グループ」を参照Microsoft 365 Business Premium)。
   - ポリシーを別のデバイス グループに適用するには、[既存のグループを使用 **する] を選択します**。

   ポリシーを受信するデバイス グループを指定した後、[次へ] を選択 **します**。

7. [構成設定 **] タブで** 、設定を確認します。 必要に応じて、ポリシーの設定を編集できます。 このタスクのヘルプを表示するには、次の記事を参照してください。 

   - [次世代の構成設定について](../security/defender-business/mdb-next-gen-configuration-settings.md)   
   - [ファイアウォールの設定](../security/defender-business/mdb-firewall.md)

   次世代の保護設定を指定した後、[次へ] を **選択します**。

8. [ポリシー **の確認] タブで** 、一般的な情報、対象デバイス、および構成設定を確認します。 

   - [編集] を選択して、必要な変更を **行います**。
   - 続行する準備ができたら、[ポリシーの更新] **を選択します**。

## <a name="create-a-new-device-protection-policy"></a>新しいデバイス保護ポリシーを作成する

1. ポータル () にMicrosoft 365 Defenderし[https://security.microsoft.com](https://security.microsoft.com)、サインインします。 

2. ナビゲーション ウィンドウで、[デバイス構成] **を選択します**。 ポリシーは、オペレーティング システム (Windows **クライアントなど)** とポリシーの種類 (次世代保護やファイアウォールなど) **によって** 編成 **されます**。 

3. オペレーティング システム タブ (クライアントなど) を **Windows** し、次に次世代保護ポリシーの一覧 **を** 確認します。 

4. [ **次世代の保護] または [ファイアウォール]** **で、[**+ 追加] **を選択します**。

5. [全般情報 **] タブ** で、次の手順を実行します。

   1. 名前と説明を指定します。 この情報は、後でユーザーとチームがポリシーを識別するのに役立ちます。
   2. ポリシーの順序を確認し、必要に応じて編集します。 (詳細については、「ポリシーの順序 [」を参照](../security/defender-business/mdb-policy-order.md)してください)。
   3. **次へ** を選択します。 

7. [デバイス グループ **] タブ** で、新しいデバイス グループを作成するか、既存のグループを使用します。 ポリシーは、デバイス グループを介してデバイスに割り当てられます。 以下に注意する必要があるものがあります。

   - 最初は、組織のユーザーが組織のデータと電子メールにアクセスするために使用しているデバイスを含む、既定のデバイス グループのみを持っている可能性があります。 既定のデバイス グループを保持して使用できます。
   - 既定のポリシーとは異なる特定の設定を持つポリシーを適用する新しいデバイス グループを作成します。 
   - デバイス グループを設定するときに、オペレーティング システムのバージョンなど、特定の条件を指定します。 条件を満たすデバイスは、除外しない限り、そのデバイス グループに含まれます。 
   - 定義する既定のデバイス グループとカスタム デバイス グループを含むすべてのデバイス グループは、Azure Active Directory (Azure AD) に格納されます。

   デバイス グループの詳細については、「 [Microsoft Defender for Business のデバイス グループ」を参照してください](../security/defender-business/mdb-create-edit-device-groups.md)。

8. [構成 **設定] タブ** で、ポリシーの設定を指定し、[次へ] を選択 **します**。 個々の設定の詳細については、「Microsoft Defender for Business の次世代構成設定について [」を参照してください](../security/defender-business/mdb-next-gen-configuration-settings.md)。

9. [ポリシー **の確認] タブで** 、一般的な情報、対象デバイス、および構成設定を確認します。 

   - [編集] を選択して、必要な変更を **行います**。
   - 続行する準備ができたら、[ポリシーの作成] **を選択します**。


## <a name="next-steps"></a>次の手順

[デバイス グループ (Microsoft 365 Business Premium](m365bp-device-groups-mdb.md)