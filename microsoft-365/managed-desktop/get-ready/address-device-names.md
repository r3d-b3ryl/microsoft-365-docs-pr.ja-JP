---
title: アドレス デバイス名の依存関係
description: デバイス名への依存関係を削除するか、例外を要求する
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: dc79cca2f68a80d9f7e7d9a09fd6d2be147d0199
ms.sourcegitcommit: d4797cfc15c732f1a7ef21e4f944e672a7170f9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2022
ms.locfileid: "62444643"
---
# <a name="address-device-name-dependency"></a>アドレス デバイス名の依存関係

Microsoft Managed Desktop は、デバイスの登録時に標準化された名前形式を適用します。 名前が後で変更された場合、Microsoft Managed Desktop はデバイスの名前を自動的に変更します。 詳細については、「デバイス名 [」を参照してください](../service-description/device-names.md)。

> [!IMPORTANT]
> 環境が特定のデバイス名 (たとえば、特定のネットワーク構成をサポートする場合) に依存している場合は、Microsoft Managed Desktop に登録する前に、その依存関係を削除するオプションを調査する必要があります。 名前の依存関係を維持する必要がある場合は、管理者ポータルから要求を[](../working-with-managed-desktop/admin-support.md)送信して、名前の変更機能を無効にし、目的の名前の形式を使用できます。

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop の準備をする手順

1. [Microsoft マネージド デスクトップの前提条件](prerequisites.md)を確認します。
1. [準備状況の評価ツール](readiness-assessment-tool.md)を実行します。
1. [ポータル サイト](../get-started/company-portal.md)を購入します。
1. [ゲスト アカウントの前提条件](guest-accounts.md)を確認します。
1. [ネットワーク構成](network.md)をチェックします。
1. [証明書とネットワーク プロファイル](certs-wifi-lan.md)を準備します。
1. [データへのユーザー アクセスを準備します](authentication.md)。
1. [アプリを準備します](apps.md)。
1. [マップ済みドライブを準備します](mapped-drives.md)。
1. [印刷リソースを準備します](printing.md)。
1. アドレス デバイス名 (この記事)。
