---
title: Microsoft Microsoft Projectデスクトップ デバイスにVisioまたは Microsoft のデバイスをインストールする
description: Microsoft Managed Desktop デバイスMicrosoft Projectまたは Microsoft Visioのインストールに関する情報
keywords: Microsoft Managed Desktop、Microsoft 365、Microsoft Project、Microsoft Visio
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
---

# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Microsoft Microsoft Projectデスクトップ デバイスにVisioまたは Microsoft のデバイスをインストールする

Microsoft Projectおよび Microsoft Visioは、Microsoft マネージ デスクトップ デバイスにインストールする特定の手順が必要です。 この記事では、これらのアプリケーションの前提条件とインストール プロセスについて説明します。

## <a name="prerequisites"></a>前提条件

管理者は、次の前提条件を満たしていることを確認する必要があります。

| 前提条件 | 説明 |
| ------ | ------ |
| ライセンスの数量 | ユーザーが使用できるMicrosoft Projectライセンスと Microsoft Visioライセンスの正しい量を指定する必要があります。 Microsoft Managed Desktop は現在、これらのアプリケーションの 64 ビット バージョンのみをサポートしています。 |
| ライセンス名 | これらのアプリケーションの適切なライセンス名は次のとおりです。 <ul><li>**Microsoft Project** - Project Online ProfessionalまたはProject Online Premium</li><li>**Microsoft Visio** - Visio オンライン プラン 2</li><ul> |
| ポータル サイト | ユーザーポータル サイトこれらのアプリケーションをインストールするには、テナントで使用できる必要があります。 テナントにポータル サイト展開されていない場合は、「ポータル サイト」 [を参照してください](company-portal.md)。 |

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Microsoft Project デスクトップ Visioの展開と展開

Microsoft Managed Desktop は、Microsoft Projectと Microsoft Visio Win32 アプリケーションを 2 つのアプリケーションとして追加Microsoft Intune。 また、2 つのグループを作成Azure Active Directory。 グループは、"Available" インテントを持つ対応するアプリケーションに割り当てられます。

**次のProjectを展開Visio。**

ユーザーを適切なグループに追加すると、アプリケーションがアプリケーションで使用ポータル サイト。 同期に数分かかる場合がありますが、ユーザーはアプリをアプリからインストールポータル サイト。

Azure ADグループ名 | どのユーザーを割り当てるか。
 --- | ---
モダン Workplace-Office-Project_Install | 必要なユーザー Project
モダン Workplace-Office-Visio_Install | 必要なユーザー Visio

## <a name="communicate-changes"></a>変更を伝える

IT 管理者は、ユーザーにインストール方法とインストール方法をユーザーに知Project重要Visio。 この通信には、次の情報が含まれます。

- これらのアプリケーションが使用可能な場合にユーザーに通知します。
- これらのアプリケーションをインストールする方法については、ポータル サイト。
