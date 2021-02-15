---
title: Microsoft OneDrive
description: Microsoft マネージド デスクトップで登録済みデバイス用に OneDrive をセットアップする方法
keywords: Microsoft マネージド デスクトップ, Microsoft 365, サービス, ドキュメント, アプリ, 業務アプリ, LOB アプリ
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 6cd2c993e0ca9d4c456a2914b866b65b59799afa
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233924"
---
# <a name="microsoft-onedrive"></a>Microsoft OneDrive

Microsoft マネージド デスクトップは、すべての Microsoft マネージド デスクトップ デバイスのクラウド ストレージ サービスとして [OneDrive for Business](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise) を使用して、デバイスが可能な限りステートレスな状態を確保します。 ユーザーは、サインインするデバイスに関係なく、ファイルを見つける可能性があります。 たとえば、Microsoft マネージド デスクトップ デバイスを新しいデバイスに置き換える場合、ファイルは自動的に新しいデバイスと同期されます。

Microsoft マネージド デバイスでは、既定でこれらの設定が自動的に構成されます。

- OneDrive は、ユーザー アカウントを使用してサイレント モードで構成され、Windows へのサインインに使用されたユーザー アカウントに自動的にサインインします (ユーザーの操作は必要としません)。 詳細については、「ユーザー アカウントの [サイレント構成 - OneDrive」を参照してください。](https://docs.microsoft.com/onedrive/use-silent-account-configuration)

- ファイル オンデマンド機能が有効になっているので、ユーザーはディスク領域を不必要に使わずに OneDrive のクラウド ストレージからファイルにアクセスできます。 詳しくは [、「Windows 10 用 OneDrive ファイル](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)オンデマンドでのディスク領域の節約」をご覧ください。

- 既知のフォルダー移動機能は、クラウド内のユーザーのデータをバックアップするためにサイレント モードで有効になっています。これにより、ユーザーは任意のデバイスからファイルにアクセスできます。 詳細については [、「OneDrive でドキュメント、](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)画像、デスクトップ フォルダーをバックアップする」を参照してください。

- ユーザーは、既知のフォルダー移動機能を無効にしたり、既知のフォルダーの場所を変更したりして、Microsoft マネージド デスクトップ デバイス間で一貫したエクスペリエンスを確保することはできません。

## <a name="user-experience"></a>ユーザー エクスペリエンス

Microsoft マネージド デスクトップのユーザーは、新しいデバイスを受け取ると、デバイスのセットアップ中に Azure 資格情報を入力して初回実行時のエクスペリエンスを実行します。 このプロセスが完了すると、ユーザーはデスクトップにアクセスして OneDrive エクスペリエンスを利用できます。

1. システムは、OneDrive が構成され、自動的に OneDrive にサインインされていることをユーザーに伝える。

:::image type="content" source="media/onedrive-sync.png" alt-text="OneDrive を同期中で、OneDrive でファイルを編集できるという通知が表示されます。ファイルを表示するには、ここをクリックしてください":::

2. システムは、OneDrive の既知のフォルダー移動が構成されていることをユーザーに伝えます。

:::image type="content" source="media/onedrive-folders.png" alt-text="IT 部門が重要なフォルダーをバックアップしたという通知。フォルダーが OneDrive にバックアップされ、他のデバイスから利用できる":::

3. デバイスがリセットまたは再イメージ化されているときに、デスクトップ上の重複するアイコンが表示されるのを防ぐため、システムは、エクスプローラーのこのビューに示すように、OneDrive 同期から Microsoft Edge と Microsoft Teams のアイコンを自動的に削除します。

:::image type="content" source="media/onedrive-teams.png" alt-text="オフのチェック ボックスとホバー テキストが表示された、Teams と Edge の一覧を表示するエクスプローラー (同期から除外)":::


## <a name="onedrive-sync-restrictions"></a>OneDrive の同期の制限

OneDrive の同期を制限する必要がある場合は、Azure Active Directory の条件付きアクセス ポリシーを使用してアクセスを制御することをお勧めします。 詳細については [、「OneDrive 同期アプリで条件付きアクセスのサポートを有効にする」を参照してください](https://docs.microsoft.com/onedrive/enable-conditional-access)。

組織で Azure の条件付きアクセス ポリシー AD使用できない場合、IT 管理者は次の手順に従う必要があります。

1. まだご存知ない場合は [、「Microsoft 365](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id)テナント ID を検索する」の説明に従ってテナント ID を検索します。
2. OneDrive 管理センターにサインインし、左側のウィンドウで **[** 同期] を選択します。 [特定 **のドメイン** に参加している PC でのみ同期を許可する] チェック ボックスをオンにし、ドメインの一覧にテナント ID を追加します。 詳細については、「特定の [ドメインに参加しているコンピューターでのみ同期を許可する」を参照してください](https://docs.microsoft.com/onedrive/allow-syncing-only-on-specific-domains)。

> [!NOTE]
> このガイダンスは、Microsoft マネージド デスクトップのテナントにのみ適用されます。 この記事では説明していない他の設定も使用されています。
