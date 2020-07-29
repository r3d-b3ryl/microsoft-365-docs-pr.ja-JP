---
title: アプリ制御の使用を開始する
description: ''
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 431e6cb3b8d7ab7e1dd317918fab4821889c7d4e
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430461"
---
# <a name="get-started-with-app-control"></a>アプリ制御の使用を開始する

ご使用の環境でアプリの制御を有効にする前に、 [Microsoft Managed Desktop が it](../service-description/app-control.md)と自分の役割と責任をどのように実装しているかを確認し、理解しておいてください。

Microsoft マネージドデスクトップは、セキュリティで保護された基本ポリシーを取得するためのより困難な側面を考慮することによって、アプリの制御を簡素化します。 IT 管理者は、テストリングでアプリをテストして、警告やエラーのログを確認する必要があります。 アプリで除外が必要な場合は、最初に検出したユーザーに応じて、要求をファイルにすることも、Microsoft Managed Desktop 操作を実行することもできます。

## <a name="initial-deployment-of-apps"></a>アプリの初期展開

最初にアプリを展開するときに、Microsoft マネージドデスクトップは現在の動作を評価する必要があります。 アプリコントロールを有効にするための正確な手順は、デバイスが環境に展開されているかどうかによって異なります。

### <a name="devices-not-yet-in-use"></a>まだ使用されていないデバイス

まだ使用しているデバイスがない場合は、Microsoft マネージドデスクトップ操作を使用してサービスチケットを開いて、アプリのコントロールを有効にするように要求します。 このスケジュールに従って、ポリシーは展開グループに段階的に展開されます。

|展開グループ  |ポリシーの種類  |Timing  |
|---------|---------|---------|
|テスト     |  監査       |  0日       |
|第 1     | Enforced        | 1 日目        |
|高速     | Enforced        |  2 日目       |
|広範な質問     | Enforced        |  3 日目       |

いつでも別のサービス要求を開いて、いつでもこの展開の一部を停止またはロールバックすることができます。

### <a name="devices-already-in-use"></a>デバイスは既に使用されています

少なくとも1つの Microsoft Managed Desktop デバイスが使用されている場合は、次の手順を実行します。

1. アプリコントロールを有効にすることを要求する Microsoft マネージドデスクトップ操作を使用してサービスチケットを開きます。 操作によって、すべてのデバイスに[監査ポリシー](../service-description/app-control.md#audit-policy)が展開されます。
2. [アプリケーションをテスト](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app)して、ブロックされるものがないかどうかを確認します。 アプリケーションがブロックされる場合は、[署名者の要求](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer)を開きます。 
3. テストが完了し、結果が何であっても、操作を通知し、保留中の署名者の要求を記録します。 このスケジュールに従って、ポリシーは展開グループに段階的に展開されます。

|展開グループ  |ポリシーの種類  |Timing  |
|---------|---------|---------|
|テスト     |  監査       |  0日       |
|第 1     | Enforced        | 1 日目        |
|高速     | Enforced        |  一時停止、要求でのロールアウト       |
|広範な質問     | Enforced        |  一時停止、要求でのロールアウト       |

いつでも別のサービス要求を開いて、いつでもこの展開の一部を停止またはロールバックすることができます。



