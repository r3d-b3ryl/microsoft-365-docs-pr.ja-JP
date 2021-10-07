---
title: Microsoft OneDrive
description: 登録Microsoft マネージド デスクトップデバイスOneDrive設定する方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント、アプリ、line-of-business アプリ、LOB アプリ
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a599f36692cbca6cbf67ddfd4a6ca1c05e02351f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60214035"
---
# <a name="microsoft-onedrive"></a>Microsoft OneDrive

Microsoft マネージド デスクトップデバイス[OneDrive for Business](/onedrive/plan-onedrive-enterprise)クラウド ストレージ サービスとして使用して、デバイスが可能なMicrosoft マネージド デスクトップ状態を確保します。 ユーザーは、サインインするデバイスに関係なく、ファイルを見つける可能性があります。 たとえば、新しいデバイスにMicrosoft マネージド デスクトップすると、ファイルは自動的に新しいデバイスに同期されます。

Microsoft Managed Devices では、既定でこれらの設定が自動的に構成されます。

- OneDriveアカウントでサイレント モードで構成され、ユーザー アカウントへのサインインに使用されたユーザー アカウントに (ユーザー操作なしで) 自動的にサインインWindows。 詳細については、「ユーザー アカウント[のサイレント構成 - ユーザー アカウントの構成」を参照OneDrive](/onedrive/use-silent-account-configuration)

- Files-On-Demand 機能が有効になっているので、ユーザーはディスク領域を不必要に使用することなく、OneDriveのクラウド ストレージからファイルにアクセスできます。 詳細については、「Save [disk space with OneDrive Files On-Demand for Windows 10」 を参照してください](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)。

- 既知のフォルダー移動機能は、クラウド内のユーザーのデータをバックアップするためにサイレント モードで有効になっています。これにより、ユーザーは任意のデバイスからファイルにアクセスできます。 詳細については、「ドキュメント、[ピクチャ](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)、デスクトップ フォルダーをバックアップする」を参照OneDrive。

- ユーザーは、既知のフォルダー移動機能を無効にしたり、既知のフォルダーの場所を変更して、デバイス間で一貫性のあるエクスペリエンスMicrosoft マネージド デスクトップすることはできません。

## <a name="user-experience"></a>ユーザー エクスペリエンス

ユーザー Microsoft マネージド デスクトップ新しいデバイスを受け取ると、デバイスのセットアップ中に Azure 資格情報を入力して、初回実行のエクスペリエンスを実行します。 このプロセスが完了すると、デスクトップにアクセスし、ユーザーエクスペリエンスをOneDriveできます。

1. システムは、ユーザー OneDrive構成済みであり、ユーザーが自動的にユーザーにサインインOneDrive。

:::image type="content" source="media/onedrive-sync.png" alt-text="通知の読み取りで、OneDrive同期中でファイルを編集OneDrive。ファイルを表示するには、ここをクリックします。":::

2. システムは、既知のフォルダー OneDriveが構成されていることをユーザーに伝えます。

:::image type="content" source="media/onedrive-folders.png" alt-text="IT 部門が重要なフォルダーをバックアップしたという通知を読み取ります。これで、フォルダーがバックアップされ、OneDriveデバイスから使用できます。":::

3. デバイスがリセットまたは再イメージ化されている場合にデスクトップ上の重複するアイコンを防止するために、エクスプローラーのこのビューに示すように、Microsoft Edge アイコンと Microsoft Teams アイコンが自動的に OneDrive 同期 から削除されます。

:::image type="content" source="media/onedrive-teams.png" alt-text="エクスプローラーで、Teamsとエッジの一覧が表示され、チェック ボックスがオフで、テキストのホバー値が [同期から除外] と表示されます。":::


## <a name="onedrive-sync-restrictions"></a>OneDrive 同期制限

アクセスを制限する必要があるOneDrive 同期、条件付きアクセス ポリシーを使用してアクセスAzure Active Directoryすることをお勧めします。 詳細については、「アプリで条件付[きアクセスのサポートを有効にする」をOneDrive 同期してください](/onedrive/enable-conditional-access)。

組織で Azure ADポリシーを使用できない場合、IT 管理者は次の手順を実行する必要があります。

1. まだ分からない場合は、「テナント ID の検索」の説明に従って、テナント[ID をMicrosoft 365します](/onedrive/find-your-office-365-tenant-id)。
2. 管理者センターにサインインOneDriveし、左側のウィンドウで **[同期**] を選択します。 [特定 **のドメイン** に参加している PC でのみ同期を許可する] チェック ボックスをオンにし、ドメインの一覧にテナント ID を追加します。 詳細については、「特定のドメインに参加しているコンピューターでのみ同期を許可 [する」を参照してください](/onedrive/allow-syncing-only-on-specific-domains)。

> [!NOTE]
> このガイダンスは、ユーザーのテナントにのみMicrosoft マネージド デスクトップ。 この記事では説明していない他の設定が使用されています。