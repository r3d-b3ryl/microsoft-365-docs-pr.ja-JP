---
title: Microsoft OneDrive
description: Microsoft Managed Desktop が登録済みデバイスOneDrive設定する方法
keywords: Microsoft Managed Desktop、Microsoft 365、サービス、ドキュメント、アプリ、line-of-business アプリ、LOB アプリ
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
---

# <a name="microsoft-onedrive"></a>Microsoft OneDrive

Microsoft Managed Desktop [は、OneDrive for Business](/onedrive/plan-onedrive-enterprise) Microsoft 管理デスクトップ デバイスのクラウド ストレージ サービスとして使用します。 これにより、デバイスが可能な限りステートレスになります。 ユーザーは、サインインするデバイスに関係なく、ファイルを検索できます。 たとえば、Microsoft Managed Desktop デバイスを新しいデバイスに置き換える場合、ファイルは自動的に新しいデバイスに同期されます。

Microsoft Managed Devices では、既定でこれらの設定が自動的に構成されます。

| 機能 | 説明 |
| ------ | ------ |
| サイレント構成 | OneDriveアカウントでサイレント モードで構成されている場合。 ユーザー操作なしで、ユーザー アカウントへのサインインに使用されたユーザー アカウントに自動的にサインインWindows。 詳細については、「ユーザー アカウント[をサイレントで構成する - OneDrive](/onedrive/use-silent-account-configuration) |
| Files-On-Demand | Files-On-Demand 機能を使用すると、ユーザーはディスク領域を不必要に使用することなく、OneDriveのクラウド ストレージからファイルにアクセスできます。 詳細については、「Save [disk space with OneDrive Files On-Demand for Windows 10」 を参照してください](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)。 |
| Known Folder Move | 既知のフォルダー移動機能は、クラウド内のユーザーのデータをバックアップするためにサイレント モードで有効になっています。これにより、ユーザーは任意のデバイスからファイルにアクセスできます。 詳細については、「ドキュメント、[ピクチャ](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)、デスクトップ フォルダーをバックアップする」を参照OneDrive。 <p> ユーザーは、既知のフォルダー移動機能を無効にしたり、既知のフォルダーの場所を変更したりして、Microsoft Managed Desktop デバイス全体で一貫性のあるエクスペリエンスを確保することはできません。</p>|

## <a name="user-experience"></a>ユーザー エクスペリエンス

Microsoft Managed Desktop ユーザーが新しいデバイスを受け取ると、デバイスのセットアップ中に Azure 資格情報を入力して、初回実行のエクスペリエンスを実行します。 このプロセスが完了すると、デスクトップにアクセスし、ユーザーエクスペリエンスをOneDriveできます。

1. システムは、ユーザー OneDrive構成済みであり、ユーザーが自動的にユーザーにサインインOneDrive。

:::image type="content" source="media/onedrive-sync.png" alt-text="同期中の通知を読み取り、OneDriveでファイルを編集できます。OneDriveをクリックしてファイルを表示します。":::

2. システムは、既知のフォルダー OneDriveが構成されていることをユーザーに伝えます。

:::image type="content" source="media/onedrive-folders.png" alt-text="IT 部門が重要なフォルダーをバックアップしたという通知を読み取ります。これで、フォルダーがバックアップされ、OneDriveデバイスから使用できます。":::

3. デバイスがリセットまたは再イメージ化されると、デスクトップ上のアイコンが重複しMicrosoft Edge、Microsoft Teamsアイコンが自動的にOneDrive 同期。この情報はエクスプローラーに表示されます。

:::image type="content" source="media/onedrive-teams.png" alt-text="エクスプローラーで、Teamsとエッジの一覧が表示され、チェック ボックスがオフで、テキストのホバー値が [同期から除外] と表示されます。":::

## <a name="onedrive-sync-restrictions"></a>OneDrive 同期制限

ポリシーを制限する必要があるOneDrive 同期、条件付きアクセス ポリシーを使用してアクセスAzure Active Directoryすることをお勧めします。 詳細については、「アプリで条件付きアクセスのサポートを[有効にするOneDrive 同期してください](/onedrive/enable-conditional-access)。

組織で条件付きアクセス ポリシー Azure AD使用できない場合、IT 管理者は次の手順を実行する必要があります。

1. まだ分からない場合は、「テナント ID を検索する」の説明に従って、テナント [ID をMicrosoft 365してください](/onedrive/find-your-office-365-tenant-id)。
1. 管理者センターにサインインOneDriveします。
1. 左側のウィンドウで、[同期] を **選択します**。
1. [特定の **ドメインに参加している PC** でのみ同期を許可する] チェック ボックスをオンにし、ドメインの一覧にテナント ID を追加します。 詳細については、「特定のドメインに参加しているコンピューターでのみ同期を許可 [する」を参照してください](/onedrive/allow-syncing-only-on-specific-domains)。

> [!NOTE]
> このガイダンスは、Microsoft Managed Desktop のテナントにのみ適用されます。 この記事では説明していない他の設定が使用されています。
