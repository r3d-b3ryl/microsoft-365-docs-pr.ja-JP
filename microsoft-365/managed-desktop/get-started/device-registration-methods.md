---
title: Microsoft Managed Desktop のデバイス登録方法
description: Microsoft Managed Desktop のデバイス登録方法に関する情報
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 7d0cabc0a9d11d337e5adabde568bd2a56ceca86
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63319122"
---
# <a name="device-registration-methods"></a>デバイス登録方法

Microsoft が Microsoft Managed Desktop でデバイスを管理するには、サービスに登録されているデバイスが必要です。

## <a name="registration-process"></a>登録プロセス

Microsoft Managed Desktop は、デバイス登録ワークフロー Windows自動パイロット サービスによって提供されます。 デバイスの登録に成功するには、次の 2 段階のプロセスが必要です。

1. デバイスの一意のハードウェア ID (ハードウェア ハッシュと呼ばれる) がキャプチャされ、Autopilot サービスにアップロードされます。
1. デバイスは、テナント ID にAzure Active Directoryされます。

どちらの手順も、デバイスが購入された OEM、リセラー、またはディストリビューターによって実行されるのが理想的です。 OEM または他のデバイス プロバイダーは、登録承認プロセスを使用して、ユーザーに代わってデバイス登録を実行します。

## <a name="registration-methods"></a>登録方法

新規または既存のデバイスからハードウェア ID を収集し、手動でアップロードすることで、組織内で登録を実行することもできます。 Microsoft Managed Desktop がサポートするデバイス登録方法を以下に示します。

- OEM の登録
    - [パートナー ポータルの使用](partner-registration.md#register-devices-using-the-partner-center)
    - [OEM API の使用](partner-registration.md#register-devices-by-using-the-oem-api)
- [手動登録](manual-registration.md)
- [既存のデバイスの手動登録](manual-registration-existing-devices.md)

## <a name="recommended-resources"></a>推奨されるリソース

- [Windows Autopilot の概要](/mem/autopilot/windows-autopilot)
- [Windowsの登録の概要](/mem/autopilot/registration-overview)

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft Managed Desktop の使用を開始する手順

1. [管理ポータル](access-admin-portal.md)にアクセスします。
1. [管理ポータルで管理者の連絡先を追加および確認する](add-admin-contacts.md)。
1. [登録後に設定を調整する](conditional-access.md)。
1. [Intune ポータル サイト](company-portal.md)を展開して割り当てます。
1. [ライセンスを割り当てる](assign-licenses.md)。
1. [アプリを展開する](deploy-apps.md)。
1. [デバイスを準備します](prepare-devices.md)。
1. [Autopilot と登録ステータス ページの初回実行時エクスペリエンス](esp-first-run.md)のセットアップ。
1. [ユーザー サポート機能を有効にする](enable-support.md)。
1. [ユーザーがデバイスを使えるようにする](get-started-devices.md)。
1. [アプリ制御の使用を開始する](get-started-app-control.md)。
