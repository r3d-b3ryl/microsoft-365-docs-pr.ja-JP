---
title: 共有デバイス
description: 共有デバイス モードの使用方法と使用時間
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
ms.openlocfilehash: 5ed7373bdcf9a8f2c8eda53c0bd249c6ba825992
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63525586"
---
# <a name="shared-devices"></a>共有デバイス

Microsoft Managed Desktop を使用すると、ユーザーが提供する共有デバイス モードと同様に、デバイスを "共有[デバイス モード" で登録Microsoft Intune](/mem/intune/configuration/shared-user-device-settings)。

このモードのデバイスは、ユーザーが単一のデスクに縛られ、頻繁にデバイスを変更する状況に合って最適化されています。 たとえば、銀行の担当者や看護スタッフなどの最前線の労働者。 このモードでは、Microsoft [Managed Desktop プロファイル](profiles.md) をデバイスに適用できます。 このモードで登録されているデバイスには、いくつかの重要な違いがあります。

- [デバイス ストレージ](#device-storage) は、共有ユーザー向けに最適化されています。
- [非アクティブなアカウント](#deletion-of-inactive-accounts) は削除されます。
- [ゲスト アカウント](#guest-accounts) は既定ではサポートされていません。
- [Microsoft 365エンタープライズ ライセンス](#microsoft-365-apps-for-enterprise)用のアプリケーションは、共有デバイス用に最適化されています。

Microsoft Managed Desktop の登録時点で共有デバイス モードを使用する選択を行うので、後でこのモードを変更する場合は、そのデバイスを登録し直して、もう一度登録する必要があります。

## <a name="when-to-use-shared-device-mode"></a>共有デバイス モードを使用する場合

ユーザーが頻繁にデバイスを変更している状況。

たとえば、銀行の担当者は 1 か所で預金を管理している場合がありますが、住宅ローンを抱える顧客を支援するためにバック オフィスに移動します。 これらの各場所で、デバイスは異なるアプリケーションを実行し、複数のユーザーが使用しますが、それらのタスクに最適化されています。

看護スタッフは、通常、患者と対話する間、部屋とオフィスの間を移動します。 オフィスのワークステーションにサインインできますが、リモート デスクトップに接続してメモを取り、別の患者と別の部屋でこのプロセスを繰り返します。

## <a name="when-not-to-use-shared-device-mode"></a>共有デバイス モードを使用しない場合

共有デバイス モードは、次のような状況では良い選択ではありません。

- ユーザーのファイルをクラウドではなくローカルに保存する必要がある場合
- デバイス上のユーザーごとにユーザー エクスペリエンスが異なる必要がある場合
- 各ユーザーが必要とする一連のアプリケーションが大きく異なる場合

## <a name="enroll-new-devices-in-shared-device-mode"></a>共有デバイス モードで新しいデバイスを登録する

ユーザーまたはパートナーが登録を処理している場合でも、共有デバイス モードを使用できます。

デバイスを自分で登録する場合は、「手動登録」の [](../get-started/manual-registration.md)手順に従って、デバイスをモダン ワークプレース デバイス - 共有デバイス モード グループ **に追加** します。

> [!WARNING]
> このグループに追加するだけで、既存の Microsoft Managed Desktop デバイスを共有デバイス モードに変換しようとはしません。 適用されるポリシーによって、ファイルOneDrive完全に失われる可能性があります。

パートナーがデバイスを登録する場合は、「パートナー登録」の手順 [](../get-started/partner-registration.md)に従い、次の表に示すようにグループ タグに **-Shared** を追加します。

| デバイス プロファイル | Autopilot グループ タグ (標準モード) | グループ タグ (共有デバイス モード) |
| ----- | ----- | ----- |
| 機密性の高いデータ | Microsoft365Managed_SensitiveData |  Microsoft365Managed_SensitiveData-Shared |
| Power User | Microsoft365Managed_PowerUser | サポート対象外 |
| Standard  | Microsoft365Managed_Standard | Microsoft365Managed_Standard-Shared |

## <a name="consequences-of-shared-device-mode"></a>共有デバイス モードの結果

### <a name="device-storage"></a>デバイス ストレージ

共有デバイスのユーザーは、データをクラウドにバックアップして、他のデバイスにフォローできる必要があります。 共有デバイス モードでデバイスを登録したら、OneDriveの Files [On-Demand](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e#:~:text=%20Turn%20on%20Files%20On-Demand%20%201%20Make,files%20as%20you%20use%20them%20box.%20More%20) および既知のフォルダー リダイレクト機能[を有効にしてください](/onedrive/redirect-known-folders)。 この方法では、各ユーザー プロファイルがデバイス ストレージに与える影響を最小限に抑えます。 共有デバイス モードのデバイスは、空きディスク領域が 25% を下回ると、ユーザー プロファイルを自動的に削除します。 このアクティビティは、記憶域が重大に制限されない限り、デバイスの現地時間の午前 0 時にスケジュールされます。

Microsoft Managed Desktop では [、SharedPC](/mem/intune/configuration/shared-user-device-settings-windows) CSP を使用してこれらの操作を実行します。そのため、これらの CSP は自分で使用しなかってください。

> [!IMPORTANT]
> 大きなファイルをダウンロードした後で、サインアウトする前にファイルに緑色のチェック アイコンが表示される必要があるユーザーをトレーニングします。クリーンアップ操作の一環としてアカウントが削除され、ファイルが OneDrive で完全にアップロードされていない場合、ファイルは完全に失われます。

### <a name="deletion-of-inactive-accounts"></a>非アクティブなアカウントの削除

共有デバイス モードでは、30 日間以上サインインしていないアカウントが削除されます。

### <a name="guest-accounts"></a>ゲスト アカウント

共有デバイス モードのデバイスでは、ドメインに参加しているアカウントのみを許可します。 デバイスにゲスト アカウントが必要な場合は、変更要求を[](../working-with-managed-desktop/admin-support.md)送信して有効にできます。

### <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise

[Microsoft 365 Apps for enterprise](/microsoft-365/managed-desktop/get-started/m365-apps)、特定のユーザーがそれらのアプリを同時に 5 つのデバイスにのみインストールできます。 共有デバイス モードでは、アプリは制限にカウントされませんので、デバイス間のローミング中に使用できます。 アプリケーションの展開と更新Microsoft 365 Apps for enterprise通常どおり動作します。

### <a name="device-profiles"></a>デバイス プロファイル

共有デバイス モードでは、特定のデバイスに 1 つのデバイス [プロファイル](profiles.md) のみを設定できます。 また、Power User デバイス プロファイルは現在、共有デバイス モードではサポートされていません。

### <a name="apps-and-policies-assigned-to-users"></a>ユーザーに割り当てられたアプリとポリシー

共有デバイスでは、自分で管理しているアプリやポリシーを、ユーザー グループではなくデバイス グループに割り当てる必要があります。 デバイス グループに割り当てると、各ユーザーのエクスペリエンスの一貫性が向上します。 例外[は、ポータル サイト](#deploying-apps-with-company-portal)。

## <a name="limitations-of-shared-device-mode"></a>共有デバイス モードの制限事項

### <a name="windows-hello"></a>Windows Hello

Windows Helloカード エミュレーションを使用してユーザー [PIN](/windows/security/identity-protection/hello-for-business/hello-faq) を安全にキャッシュし、ユーザーが認証する必要がある回数を最小限に抑えます。 ただし、Windowsデバイスでは、一度に 10 枚のスマート カードしか使用できない場合があります。 11 番目のユーザーが初めてサインインすると、既存のアカウントの 1 つがスマート カードを失います。 サインインできますが、PIN はキャッシュされません。

### <a name="universal-print"></a>ユニバーサル 印刷

ユニバーサル印刷では、1 人のユーザーのプリンターを共有デバイスにインストールすると、そのデバイスのすべてのユーザーがプリンターを使用できます。 共有デバイス上のユーザー間でプリンターを分離する方法はありません。

## <a name="limitations-of-shared-device-mode-in-the-public-preview-release"></a>パブリック プレビュー リリースでの共有デバイス モードの制限

### <a name="primary-user"></a>プライマリ ユーザー

各Microsoft Intuneにはプライマリ ユーザーが割り当てられます。これは、デバイスが Autopilot によって設定された場合に割り当てられます。 ただし、デバイスが共有されている場合、Intune ではプライマリ ユーザーが削除される必要があります。

> [!IMPORTANT]
> 共有デバイス モードがパブリック プレビューの場合は、次の手順に従ってプライマリ ユーザーを削除してください。Microsoft エンドポイント マネージャー 管理センターにサインインし、[**DevicesAll**> デバイス] を選択し、デバイスを選択し、[**PropertiesRemove**>] プライマリ ユーザーを選択し、そこに表示されているユーザーを削除します。

### <a name="deploying-apps-with-company-portal"></a>アプリを使用してアプリを展開ポータル サイト

一部のアプリは、おそらくすべてのデバイスに存在する必要はないので、ユーザーが必要な場合にのみアプリをインストールすることを希望する場合[があります。ポータル サイト](/mem/intune/user-help/install-apps-cpapp-windows)。

Microsoft Managed Desktop は、共有ポータル サイトモードのデバイスに対して既定で無効に設定されます。 この設定を有効ポータル サイト場合は、変更要求を[送信できます](../working-with-managed-desktop/admin-support.md)。 ただし、このパブリック プレビューでは、この機能のいくつかの制限に注意する必要があります。

- アプリをユーザーが使用ポータル サイトするには、Intune のそのアプリに[](/mem/intune/apps/apps-deploy)ユーザー グループを割り当て、そのユーザー グループに各ユーザーを追加します。
- デバイスにプライマリ ユーザー [を設定できません](#primary-user)。
- ユーザーがアプリをインストールしたアプリをポータル サイト、そのデバイス上のすべてのユーザーからアプリをアンインストールする必要があります。

> [!CAUTION]
> ポータル サイト利用可能なデバイス グループに割り当てられたアプリケーションはサポートされていません。

### <a name="redeployment-of-microsoft-365-apps-for-enterprise"></a>サーバーのMicrosoft 365 Apps展開Enterprise

パブリック プレビュー中に、Microsoft 365 Apps再展開する必要がある場合、ユーザーはローカル サポート スタッフに問い合わせ、そのデバイスでエージェントの昇格と再インストールを要求Microsoft 365 Apps for enterprise必要があります。

### <a name="microsoft-teams"></a>Microsoft Teams

ユーザーが初めてTeamsを開始すると、アプリを使用する前にアプリの更新を求めるメッセージが表示されます。 更新を許可すると、Teams自体がバックグラウンドで更新されます。
