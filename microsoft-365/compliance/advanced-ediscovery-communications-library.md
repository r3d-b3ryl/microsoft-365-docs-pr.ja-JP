---
title: 管理ページのコミュニケーション ライブラリでカストディアン通信テンプレートを管理Advanced eDiscovery
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
description: 保管担当者の通信テンプレート (保留通知用テンプレートなど) を Advanced eDiscovery に追加して、組織内の任意のケースで使用できます。
ms.openlocfilehash: 1b5be4a4a923050b43943e81ac64265e16749899
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330976"
---
# <a name="manage-custodian-communications-templates-in-advanced-ediscovery"></a>管理担当者の通信テンプレートを管理Advanced eDiscovery

ユーザーまたは他のユーザーが保留通知または他の種類のカストディアン通信を作成する場合は、Advanced eDiscovery ケースの [コミュニケーション] タブのコミュニケーション エディターを使用して、通信ドキュメントを最初から作成する必要があります。 これで、組織のいかなる場合でも通信を作成するために使用できる通信テンプレートを作成できる新しい機能がリリースされました。 通信テンプレートを作成したら、ケースで使用できます。 つまり、paralegals またはカストディアン通信を作成する他のユーザーは、通知を作成するために最初から開始する必要はありません。 代わりに、テンプレートを選択して、保管担当者に送信される通知を作成できます。

この記事では、組織全体のコミュニケーション テンプレートを作成し、特定のケースに対して新しいカストディアン通知を作成するときに選択するAdvanced eDiscovery説明します。

## <a name="before-you-create-templates-in-the-communications-library"></a>コミュニケーション ライブラリでテンプレートを作成する前に

- 組織の電子情報開示管理者である必要があります。組織のコミュニケーション ライブラリでテンプレートを追加または削除Advanced eDiscovery。 詳細については、「電子情報開示アクセス[許可を割り当てる」を参照Microsoft 365 コンプライアンス センター](assign-ediscovery-permissions.md)  

- 組織には、通信ライブラリに最大 50 のテンプレートを含めできます。

## <a name="create-a-communications-template"></a>通信テンプレートの作成

1. [設定] Microsoft 365 コンプライアンス センターに移動し、[[Advanced eDiscovery] を](https://go.microsoft.com/fwlink/p/?linkid=2173764)**クリックAdvanced eDiscoveryします**。

   ![[設定Advanced eDiscovery選択]](..\media\HistoricalVersions1.png)

2. [通信ライブラリ **設定**] ページで、[通信ライブラリ **] タブを選択** します。

3. [通信ライブラリ **] ページで、[** 作成] を **クリックします**。

4. 手順に従って、カストディアン通信を作成します。 手順については、「法的ホールド通知の作成 [」を参照してください](create-hold-notification.md)。

   > [!NOTE]
   > 通信テンプレートを作成する手順は、ケース内に通知を作成するワークフローと同じです。 唯一の違いは、テンプレートを作成するときに発行担当者を指定しないし、保管担当者を割り当てない点です。 発行担当者の指定と保管担当者の割り当ては、通信テンプレートを使用してケースの保管担当者通知を作成するときに行われます。

5. テンプレートを作成すると、[通信ライブラリ] ページ **にテンプレートが表示** されます。

   ![コミュニケーション ライブラリに表示されるテンプレート](..\media\AeDCommunicationsLibrary1.png)

ユーザーまたは他の電子情報開示管理者は、通信テンプレートを編集できます。 テンプレートに加えた変更は、そのテンプレートを使用して以前に作成された通知には影響を与え、変更されません。 これらの変更は、更新されたテンプレートを使用して作成された新しい通知にのみ適用されます。

## <a name="use-a-communications-template-to-create-a-custodian-notification"></a>通信テンプレートを使用してカストディアン通知を作成する

通信ライブラリで 1 つ以上の通信テンプレートを作成した後、これらのテンプレートを選択してケース内に保管担当者通知を作成できます。

テンプレートを選択するには、

1. [電子情報開示Microsoft 365 コンプライアンス センター詳細] に移動 **>** 組織のケースの一覧を表示します。

2. ケースを選択し、[通信] **タブをクリック** し、[新しい通信] **をクリックします**。

3. [名前の **通信] ページ** で、[ **通信テンプレートの** 選択] ドロップダウン リストを使用して、カストディアン通知の作成に使用する通信テンプレートを選択します。

   組織のコミュニケーション ライブラリ内のテンプレートの一覧がドロップダウン リストに表示されます。

   ![ドロップダウン リストに表示される通信ライブラリのテンプレート。](..\media\AeDCommunicationsTemplates1.png)
