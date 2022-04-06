---
title: 共有デバイス
description: 共有デバイス モードを使用する方法とタイミング
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
ms.openlocfilehash: ad9cb5e69585f0c014050b51b719e539111cf9fa
ms.sourcegitcommit: 2f6a0096038d09f0e43e1231b01c19e0b40fb358
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64687187"
---
# <a name="shared-devices"></a>共有デバイス

Microsoft Managed Desktopでは、[Microsoft Intune](/mem/intune/configuration/shared-user-device-settings)によって提供される共有デバイス モードと同様に、デバイスを "共有デバイス モード" で登録できます。

このモードのデバイスは、ユーザーが 1 つのデスクに接続されておらず、頻繁にデバイスを変更する状況に合わせて最適化されます。 たとえば、銀行の窓口や職員などの現場の従業員などです。 このモードでは、任意のMicrosoft Managed Desktop [プロファイルを](profiles.md)デバイスに適用できます。 このモードで登録されているデバイスには、いくつかの重要な違いがあります。

- [デバイス ストレージ](#device-storage) は、共有ユーザー向けに最適化されています。
- [非アクティブなアカウント](#deletion-of-inactive-accounts) は削除されます。
- [ゲスト アカウントは](#guest-accounts) 既定ではサポートされていません。
- [Microsoft 365](#microsoft-365-apps-for-enterprise) エンタープライズ ライセンス用アプリケーションは、共有デバイス用に最適化されています。

Microsoft Managed Desktopでの登録時点で共有デバイス モードを使用するように選択しているため、後でこのモードから変更する場合は、登録を解除して再度登録する必要があります。

## <a name="when-to-use-shared-device-mode"></a>共有デバイス モードを使用する場合

ユーザーが頻繁にデバイスを変更する状況。

たとえば、銀行の窓口担当者は、1 つの場所で入金を管理しているが、住宅ローンを持つ顧客を支援するためにバック オフィスに移動する場合があります。 これらの各場所では、デバイスは異なるアプリケーションを実行し、それらのタスク用に最適化されていますが、複数のユーザーが使用します。

通常、スタッフは患者と対話する際に、部屋とオフィスの間を移動します。 オフィス内のワークステーションにサインインすることはできますが、リモート デスクトップに接続してメモを取り、別の患者と別の部屋でこのプロセスを繰り返します。

## <a name="when-not-to-use-shared-device-mode"></a>共有デバイス モードを使用しない場合

共有デバイス モードは、次の状況では適していません。

- ユーザーのファイルをクラウドではなくローカルに格納する必要がある場合
- デバイス上のユーザーごとにユーザー エクスペリエンスが異なる必要がある場合
- 各ユーザーが必要とするアプリケーションのセットが大きく異なる場合

## <a name="register-new-devices-in-shared-device-mode"></a>共有デバイス モードで新しいデバイスを登録する

2203 以降では、デバイスの登録を処理するパートナーを問わず、[Microsoft Managed DesktopでWindows Autopilot 自己展開モード プロファイルを](/mem/autopilot/self-deploying)使用することを選択できます。

デバイスを自分で登録する場合は、Windows Autopilot デバイス ブレードに新しいデバイスをインポートする必要があります。

**Windows Autopilot デバイス ブレードに新しいデバイスをインポートするには:**

1. Windows Autopilot 自己展開モード プロファイルを割り当てる新しいデバイスの[ハードウェア ハッシュ](../get-started/manual-registration.md#obtain-the-hardware-hash)を収集します。
2. [Microsoft エンドポイント マネージャー ポータル](https://endpoint.microsoft.com)に移動します。
2. 左側のナビゲーション メニューから [ **デバイス** ] を選択します。
3. [**プラットフォーム別**] セクションで、[**Windows**] を選択します。 次に、[**Windows登録**] を選択します。
4. **[Windows Autopilot Deployment プログラム**] セクションで、[デバイス] を選択 **します**。
5. 手順 1 で収集されたすべてのハードウェア ハッシュを含む.CSV ファイルを[インポート](../get-started/manual-registration.md#register-devices-by-using-the-admin-portal)します。
6. Windows Autopilot デバイスをアップロードしたら、インポートしたデバイスのグループ タグ属性を編集Microsoft Managed Desktop、Windows Autopilot 自己展開モード プロファイルを使用して登録できるようにする必要があります。 グループ タグ属性については、以下を参照してください。 次の表に示すように、グループ タグに **-Shared** を追加する必要があります。

| デバイス プロファイル | Autopilot グループ タグ (標準モード) | グループ タグ (共有デバイス モード) |
| ----- | ----- | ----- |
| 機密性の高いデータ | Microsoft365Managed_SensitiveData |  Microsoft365Managed_SensitiveData-Shared |
| Power ユーザー | Microsoft365Managed_PowerUser | サポート対象外 |
| Standard  | Microsoft365Managed_Standard | Microsoft365Managed_Standard-Shared |

> [!WARNING]
> Autopilot に以前にインポートしたデバイスに **-Shared** を追加して、グループ タブ属性を編集Windowsしないでください。 Windows Autopilot に既にインポートされているデバイスは、Microsoft365Managed_で始まるMicrosoft Managed Desktop グループ タグの 1 つを使用します *が、最初* は **-Shared** が追加されていないデバイスは、既に別のAzure Active Directory グループの一部です。 このAzure Active Directory グループには、自動パイロット自己展開モード プロファイルWindows割り当てられません。 既存のデバイスを共有デバイスとして再利用する必要がある場合は、デバイスを削除して autopilot Windows再登録する必要があります。

パートナーがデバイスを登録している場合は、「 [パートナー登録](../get-started/partner-registration.md)」の手順に従いますが、上の表に示すように、グループ タグに **-Shared** を追加します。

## <a name="consequences-of-shared-device-mode"></a>共有デバイス モードの結果

### <a name="device-storage"></a>デバイス ストレージ

共有デバイスのユーザーは、他のデバイスにデータを追跡できるように、データをクラウドにバックアップする必要があります。 共有デバイス モードでデバイスを登録したら、OneDriveの [Files On-Demand](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e#:~:text=%20Turn%20on%20Files%20On-Demand%20%201%20Make,files%20as%20you%20use%20them%20box.%20More%20) および[既知のフォルダーリダイレクト](/onedrive/redirect-known-folders)機能を有効にしてください。 この方法により、各ユーザー プロファイルがデバイス ストレージに与える影響が最小限に抑えられます。 共有デバイス モードのデバイスでは、空きディスク領域が 25% を下回ると、ユーザー プロファイルが自動的に削除されます。 このアクティビティは、ストレージが大幅に制限されない限り、デバイスのローカル時刻の午前 0 時にスケジュールされます。

Microsoft Managed Desktopは [SharedPC](/mem/intune/configuration/shared-user-device-settings-windows) CSP を使用してこれらの操作を行うので、それらの CSP は自分で使用しないようにしてください。

> [!IMPORTANT]
> 大きなファイルをダウンロードした後、サインアウトする前にファイルに緑色のチェック アイコンが表示されることを確認する必要があることをユーザーにトレーニングします。クリーンアップ操作の一環としてアカウントが削除され、ファイルがOneDriveに完全にアップロードされていない場合、ファイルは完全に失われます。

### <a name="deletion-of-inactive-accounts"></a>非アクティブなアカウントの削除

共有デバイス モードでは、30 日間以上サインインしていないアカウントが削除されます。

### <a name="guest-accounts"></a>ゲスト アカウント

共有デバイス モードのデバイスでは、ドメインに参加しているアカウントのみが許可されます。 デバイスにゲスト アカウントが必要な場合は、 [変更要求](../working-with-managed-desktop/admin-support.md) を提出して有効にするよう要求できます。

### <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise

[通常、Microsoft 365 Apps for enterprise](/microsoft-365/managed-desktop/get-started/m365-apps)では、特定のユーザーが同時に 5 台のデバイスにのみこれらのアプリをインストールできます。 共有デバイス モードでは、アプリは制限に対してカウントされないため、デバイス間のローミング中にアプリを使用できます。 Microsoft 365 Apps for enterpriseのデプロイと更新は、通常どおりに機能します。

### <a name="device-profiles"></a>デバイス プロファイル

共有デバイス モードでは、特定のデバイスに 1 つの [デバイス プロファイル](profiles.md) のみを含めることができます。 また、Power ユーザー デバイス プロファイルは現在、共有デバイス モードではサポートされていません。

### <a name="apps-and-policies-assigned-to-users"></a>ユーザーに割り当てられたアプリとポリシー

共有デバイスでは、ユーザー グループではなく、自分で管理しているアプリまたはポリシーを *デバイス グループ* に割り当てる必要があります。 デバイス グループに割り当てることで、各ユーザーのエクスペリエンスの一貫性が向上します。 例外は[ポータル サイト](#deploying-apps-with-company-portal)です。

## <a name="limitations-of-shared-device-mode"></a>共有デバイス モードの制限事項

### <a name="windows-hello"></a>Windows Hello

Windows Helloでは、スマート カード エミュレーションを使用して[ユーザー PIN を](/windows/security/identity-protection/hello-for-business/hello-faq)安全にキャッシュし、ユーザーが認証する回数を最小限に抑えます。 ただし、Windowsでは、特定のデバイスで一度に使用できるスマート カードは 10 枚のみです。 11 番目のユーザーが初めてサインインすると、既存のアカウントの 1 つがスマート カードを失います。 サインインすることはできますが、PIN はキャッシュされません。

### <a name="universal-print"></a>ユニバーサル印刷

ユニバーサル 印刷が 1 人のユーザーのプリンターを共有デバイスにインストールすると、そのプリンターはそのデバイスのすべてのユーザーが使用できるようになります。 共有デバイス上のユーザー間でプリンターを分離する方法はありません。

## <a name="limitations-of-shared-device-mode-in-the-public-preview-release"></a>パブリック プレビュー リリースでの共有デバイス モードの制限事項

### <a name="primary-user"></a>プライマリ ユーザー

各Microsoft Intuneデバイスにはプライマリ ユーザーが割り当てられます。これは、デバイスが Autopilot によって設定されたときに割り当てられます。 ただし、デバイスが共有されている場合、Intuneはプライマリ ユーザーを削除する必要があります。

> [!IMPORTANT]
> 共有デバイス モードはパブリック プレビュー段階ですが、次の手順に従ってプライマリ ユーザーを削除してください:Microsoft エンドポイント マネージャー管理センターにサインインし、**DevicesAll**> **デバイス** を選択し、デバイスを選択してから **PropertiesRemove プライマリ ユーザー****を選択**>し、そこに表示されているユーザーを削除します。

### <a name="deploying-apps-with-company-portal"></a>ポータル サイトを使用したアプリのデプロイ

一部のアプリは、すべてのデバイスに存在する必要はないので、ユーザーが必要な場合にのみそれらのアプリ[を](/mem/intune/user-help/install-apps-cpapp-windows)ポータル サイトからインストールすることをお勧めします。

Microsoft Managed Desktopは、共有デバイス モードのデバイスに対して既定でポータル サイトを無効にします。 ポータル サイトを有効にする場合は、[変更要求](../working-with-managed-desktop/admin-support.md)を提出できます。 ただし、このパブリック プレビューでは、この機能のいくつかの制限事項に注意する必要があります。

- ポータル サイトのユーザーがアプリを使用できるようにするには、Intuneでそのアプリに[ユーザー グループを割り当て](/mem/intune/apps/apps-deploy)、そのユーザー グループに各ユーザーを追加します。
- デバイスに [プライマリ ユーザー](#primary-user)を設定することはできません。
- ユーザーがポータル サイト経由でインストールしたアプリをアンインストールするには、そのデバイス上のすべてのユーザーからアプリをアンインストールする必要があります。

> [!CAUTION]
> ポータル サイトは、使用可能なデバイス グループに割り当てられたアプリケーションをサポートしていません。

### <a name="redeployment-of-microsoft-365-apps-for-enterprise"></a>EnterpriseのMicrosoft 365 Appsの再デプロイ

パブリック プレビュー中に、Microsoft 365 Appsを再デプロイする必要がある場合、ユーザーはローカル サポート スタッフに連絡してエージェントの昇格を要求し、そのデバイスにMicrosoft 365 Apps for enterpriseを再インストールする必要があります。

### <a name="microsoft-teams"></a>Microsoft Teams

ユーザーが初めてTeamsを開始すると、アプリを使用する前にアプリの更新を求めるメッセージが表示されます。 更新を許可すると、Teams自体はバックグラウンドで更新されます。
