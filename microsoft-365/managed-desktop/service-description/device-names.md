---
title: デバイス名
description: Microsoft Managed Desktop がデバイス名を管理する方法
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
ms.openlocfilehash: adf4809e0d8dc29f170475435b19092abf2062fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893892"
---
# <a name="device-names"></a>デバイス名

Microsoft Managed Desktop では、Windows Autopilot、Azure Active Directory、Microsoft Intune を使用します。 これらのサービスがシームレスに連携するには、デバイスに一貫性のある標準化された名前が必要です。 Microsoft Managed Desktop は、デバイスの登録時に標準化された名前形式 *(MMD-%RAND11* 形式) を適用します。 Windows Autopilot では、これらの名前が割り当てされます。 自動パイロットの詳細については、「Autopilot での初回実行エクスペリエンス」および「登録状態ページ」 [を参照してください](../get-started/esp-first-run.md)。

## <a name="automated-name-changes"></a>名前の自動変更

後でデバイスの名前が変更された場合、Microsoft Managed Desktop は自動的に名前を標準化された形式で新しい名前に変更します。 このプロセスは 4 時間ごとに行われます。 名前の変更は、ユーザーが次回デバイスを再起動する際に行います。

> [!IMPORTANT]
> 環境が特定のデバイス名 (たとえば、特定のネットワーク構成をサポートする場合) に依存している場合は、Microsoft Managed Desktop に登録する前に、その依存関係を削除するオプションを調査する必要があります。 名前の依存関係を維持する必要がある場合は、管理者ポータルから要求を[](../working-with-managed-desktop/admin-support.md)送信して、名前の変更機能を無効にし、目的の名前の形式を使用できます。