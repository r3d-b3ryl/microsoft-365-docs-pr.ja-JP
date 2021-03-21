---
title: Windows 10 位置情報サービス
description: デバイスで Windows 位置情報サービスを有効にする方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 210356dd21b36efbb27d8faa4f8616145584159c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929502"
---
# <a name="windows-10-location-service"></a>Windows 10 位置情報サービス

Microsoft Managed Desktop のデバイスは、Windows Autopilot を使用して登録されます。 このプロセスでは、Azure Active Directory と Microsoft Intune を使用して管理できます。 既定では、Windows 10 の位置情報サービスは、デバイスが初めて有効になっているときに無効になります。この機能が "箱から出た" エクスペリエンス中にプライバシー設定で有効になっていない限りです。 これらの設定は、Microsoft Managed Desktop での自動パイロット登録中に非表示になります。 Autopilot のセットアップ方法の詳細については、「Autopilot での初回実行エクスペリエンス」および「登録状態ページ」 [を参照してください](esp-first-run.md)。

このため、Microsoft Managed Desktop デバイスはデバイスの場所を取得できません。これにより、タイム ゾーンなど、いくつかの Windows 機能の機能が制限されます。 Windows 10 位置情報サービスの詳細については [、「Windows 10 location Service and privacy」を参照してください](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)。

Microsoft Managed Desktop に参加するために位置情報サービスを使用する必要は一方で、ユーザー エクスペリエンスは制限されます。 たとえば、デバイスは、ユーザーが別のタイム ゾーンで作業するときに、自分のタイムゾーンを自動的に判断できません。

## <a name="enable-the-location-service"></a>位置情報サービスを有効にする

デバイスを Microsoft Managed Desktop サービスに登録するときに、位置情報サービスの使用をオプトインするか、登録後にサービスをオンまたはオフにできます。

### <a name="opt-in-during-enrollment"></a>登録中にオプトインする

Microsoft Managed Desktop サービスで位置情報サービスを有効にできます。 登録シーケンス中に、Windows 10 の位置情報サービスをデバイスで有効にするかどうかを選択するかどうかを選択するメッセージが表示されます。

### <a name="control-the-location-service-after-enrollment"></a>登録後に位置情報サービスを制御する

管理ポータルからサポート要求を送信することで、いつでも位置情報サービスを有効 (または無効) [](../working-with-managed-desktop/admin-support.md) [にできます](access-admin-portal.md)。

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a>Microsoft Managed Desktop が Windows 10 の場所サービスを構成する方法

位置情報サービスの使用をオプトインする場合、ユーザーのプライバシーに影響を与えることなく、必要な最小設定を使用します。 詳細については [、「Windows 10 Location Service and privacy」を参照してください](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)。

Microsoft Managed Desktop では **、Windows** 設定の **[場所の** プライバシー設定] を [このデバイス上の場所へのアクセスを許可 **する] を有効にします**。 ユーザー インターフェイスは次のように表示されます。

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="Windows 設定の場所の設定":::

> [!NOTE]
> 位置情報サービスの使用をオプトインする場合、これは Windows オペレーティング システム自体にのみ適用されます。 アプリは位置情報サービスを使用することはできません。 各ユーザーは、アプリが自分の場所にアクセスできるかどうかを選択できます。