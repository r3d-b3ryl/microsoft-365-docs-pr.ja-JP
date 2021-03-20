---
title: Microsoft OneDrive
description: Microsoft Managed Desktop が登録済みデバイス用に OneDrive をセットアップする方法
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentation, apps, line-of-business apps, LOB apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a26500c1671afffc7b70d509a4242914631b937c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904842"
---
# <a name="microsoft-onedrive"></a>Microsoft OneDrive

Microsoft Managed Desktop は [、すべての Microsoft Managed Desktop](/onedrive/plan-onedrive-enterprise) デバイスのクラウド ストレージ サービスとして OneDrive for Business を使用して、デバイスが可能な限りステートレスな状態を確保します。 ユーザーは、サインインするデバイスに関係なく、ファイルを見つける可能性があります。 たとえば、Microsoft Managed Desktop デバイスを新しいデバイスに置き換える場合、ファイルは自動的に新しいデバイスに同期されます。

Microsoft Managed Devices では、既定でこれらの設定が自動的に構成されます。

- OneDrive は、ユーザー アカウントを使用してサイレントモードで構成され、Windows へのサインインに使用されたユーザー アカウントに (ユーザーの操作なしで) 自動的にサインインします。 詳細については、「ユーザー アカウントの [サイレント構成 - OneDrive」を参照してください。](/onedrive/use-silent-account-configuration)

- Files-On-Demand 機能が有効になっているので、ユーザーはディスク領域を不必要に使わずに OneDrive のクラウド ストレージからファイルにアクセスできます。 詳細については [、「Windows 10 用 OneDrive Files On-Demand](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)でディスク領域を節約する」を参照してください。

- 既知のフォルダー移動機能は、クラウド内のユーザーのデータをバックアップするためにサイレント モードで有効になっています。これにより、ユーザーは任意のデバイスからファイルにアクセスできます。 詳細については [、「OneDrive を使用して](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)ドキュメント、ピクチャ、デスクトップ フォルダーをバックアップする」を参照してください。

- ユーザーは、既知のフォルダー移動機能を無効にしたり、既知のフォルダーの場所を変更したりして、Microsoft Managed Desktop デバイス全体で一貫性のあるエクスペリエンスを確保することはできません。

## <a name="user-experience"></a>ユーザー エクスペリエンス

Microsoft Managed Desktop ユーザーが新しいデバイスを受け取ると、デバイスのセットアップ中に Azure 資格情報を入力して初回実行エクスペリエンスを実行します。 このプロセスが完了すると、デスクトップにアクセスして OneDrive エクスペリエンスを利用できます。

1. システムは、OneDrive が構成され、OneDrive に自動的にサインインされていることをユーザーに伝える。

:::image type="content" source="media/onedrive-sync.png" alt-text="通知の読み取りで OneDrive を同期し、OneDrive でファイルを編集できます。ファイルを表示するには、ここをクリックしてください":::

2. システムは、OneDrive 既知のフォルダー移動が構成されていることをユーザーに伝えます。

:::image type="content" source="media/onedrive-folders.png" alt-text="IT 部門が重要なフォルダーをバックアップしたという通知を読み取ります。フォルダーは OneDrive にバックアップされ、他のデバイスから利用できます。":::

3. デバイスがリセットまたは再イメージ化されている場合にデスクトップ上の重複アイコンを防止するために、エクスプローラーのこのビューに示すように、システムは OneDrive 同期から Microsoft Edge アイコンと Microsoft Teams アイコンを自動的に削除します。

:::image type="content" source="media/onedrive-teams.png" alt-text="チェック ボックスがオフの Teams と Edge のリストを表示し、同期から除外されたテキストをホバーします。":::


## <a name="onedrive-sync-restrictions"></a>OneDrive 同期の制限

OneDrive 同期を制限する必要がある場合は、Azure Active Directory 条件付きアクセス ポリシーを使用してアクセスを制御することをお勧めします。 詳細については [、「OneDrive 同期アプリで条件付きアクセスのサポートを有効にする」を参照してください](/onedrive/enable-conditional-access)。

組織で Azure ADポリシーを使用できない場合、IT 管理者は次の手順を実行する必要があります。

1. まだ分からない場合は [、「Microsoft 365](/onedrive/find-your-office-365-tenant-id)テナント ID の検索」の説明に従って、テナント ID を検索します。
2. OneDrive 管理センターにサインインし、左側のウィンドウで **[同期** ] を選択します。 [特定 **のドメイン** に参加している PC でのみ同期を許可する] チェック ボックスをオンにし、ドメインの一覧にテナント ID を追加します。 詳細については、「特定のドメインに参加しているコンピューターでのみ同期を許可 [する」を参照してください](/onedrive/allow-syncing-only-on-specific-domains)。

> [!NOTE]
> このガイダンスは、Microsoft Managed Desktop のテナントにのみ適用されます。 この記事では説明していない他の設定が使用されています。