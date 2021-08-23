---
title: アドレス デバイス名の依存関係
description: デバイス名への依存関係を削除するか、例外を要求する
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
ms.openlocfilehash: cf885a3d0bba2cf3abe85bc54f5e761f286716b9
ms.sourcegitcommit: 00a8a3376ea02770143af9a80cbe17a2b62636e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2021
ms.locfileid: "58364975"
---
# <a name="address-device-name-dependency"></a>アドレス デバイス名の依存関係

Microsoft マネージド デスクトップ登録時に標準化された名前形式が適用され、後で名前が変更された場合はデバイスの名前が自動的に変更されます。 詳細については、「デバイス名 [」を参照してください](../service-description/device-names.md)。

> [!IMPORTANT]
> 環境が特定のデバイス名 (たとえば、特定のネットワーク構成をサポートする場合) に依存している場合は、Microsoft マネージド デスクトップ に登録する前に、その依存関係を削除するオプションを調査する必要があります。 名前の依存関係を維持する必要がある場合は、管理者ポータルから要求を[](../working-with-managed-desktop/admin-support.md)送信して、名前の変更機能を無効にし、目的の名前の形式を使用できます。

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>インストールの準備を行うMicrosoft マネージド デスクトップ

1. [Microsoft マネージド デスクトップの前提条件](prerequisites.md)を確認します。
2. 準備 [状況評価ツールを実行します](readiness-assessment-tool.md)。
1. 購入[ポータル サイト](../get-started/company-portal.md).
1. ゲスト [アカウントの前提条件を確認します](guest-accounts.md)。
1. ネットワーク [構成を確認します](network.md)。
1. [証明書とネットワーク プロファイルを準備します](certs-wifi-lan.md)。
1. [データへのユーザー アクセスを準備します](authentication.md)。
1. [アプリを準備します](apps.md)。
1. [マップされたドライブを準備します](mapped-drives.md)。
1. [印刷リソースを準備します](printing.md)。
1. アドレス [デバイス名 (この記事)。