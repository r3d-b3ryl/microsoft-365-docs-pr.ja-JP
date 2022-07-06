---
title: 暗号化用の BitLocker
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: ''
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: Office 365 BitLocker 暗号化を使用して、コンピューターやディスクの紛失や盗難によるデータ盗難の可能性を減らす方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dec62da7bc4d29891dcd86ec378faeb52a2d3d9f
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66633897"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker と Distributed Key Manager (DKM) による暗号化

Microsoft サーバーは BitLocker を使用して、お客様の保存データを含むディスク ドライブをボリューム レベルで暗号化します。 BitLocker 暗号化は、Windows に組み込まれているデータ保護機能です。 BitLocker は、顧客データが含まれるディスクに何者かが物理的にアクセスできるようになりかねない過失がプロセスや制御 (アクセス制御またはハードウェアのリサイクルなど) で生じた場合に、脅威から安全に保護するために使用されるテクノロジの 1 つです。 その場合、BitLocker は、コンピューターやディスクの紛失、盗難、または不適切な廃棄によるデータの盗難や漏洩などの脅威の可能性を低減します。

BitLocker は、Exchange Online、SharePoint Online、およびSkype for Businessの顧客データを含むディスクに、Advanced Encryption Standard (AES) 256 ビット暗号化を使用して展開されます。 ディスク セクターは、ボリューム マスター キー (VMK) で暗号化されたフル ボリューム暗号化キー (FVEK) で暗号化され、サーバーのトラステッド プラットフォーム モジュール (TPM) にバインドされます。 VMK は FVEK を直接保護するため、VMK の保護が重要になります。 次の図は、特定のサーバー (この場合は、Exchange Online サーバーを使用) の BitLocker キー保護チェーンの例を示しています。

次の表では、特定のサーバー (この場合はExchange Online サーバー) の BitLocker キー保護チェーンについて説明します。

| KEY PROTECTOR | 粒 度 | 生成方法 | どこに保存されますか? | 保護 |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| AES 256 ビットの外部キー | サーバーごと | BitLocker API | TPM またはシークレット セーフ | Lockbox/Access Control |
|  |  |  | メールボックス サーバー レジストリ | TPM が暗号化されている |
| 48 桁の数値パスワード | ディスクごと | BitLocker API | Active Directory | Lockbox/Access Control |
| データ復旧エージェント (DRA) としての X.509 証明書 (公開キー保護機能とも呼ばれます) | 環境 (Exchange Online マルチテナントなど) | Microsoft CA | ビルド システム | 秘密キーの完全なパスワードを持つユーザーはいません。 パスワードは物理的な保護下です。 |


BitLocker キー管理には、Microsoft データセンター内の暗号化されたディスクのロック解除または回復に使用される回復キーの管理が含まれます。 Microsoft 365 は、審査を受けて承認された個人のみがアクセスできるセキュリティで保護された共有にマスター キーを保存します。 キーの資格情報は、アクセス制御データ ("シークレット ストア" と呼ばれる) 用のセキュリティで保護されたリポジトリに格納されます。この場合、Just-In-Time アクセス昇格ツールを使用してアクセスするには、高度な昇格と管理の承認が必要です。

BitLocker は、次の 2 つの管理カテゴリに分類されるキーをサポートしています。

- BitLocker で管理されるキーは、一般的に有効期間が短く、サーバーにインストールされているオペレーティング システムのインスタンス、または指定されたディスクの有効期間に関連付けられています。 これらのキーは、サーバーの再インストールまたはディスクのフォーマット中に削除され、リセットされます。

- BitLocker の回復キー。BitLocker の外部で管理されますが、ディスクの暗号化解除に使用されます。 BitLocker は、オペレーティング システムが再インストールされ、暗号化されたデータ ディスクがすでに存在する場合のシナリオで、回復キーを使用します。 回復キーは、応答者がディスクのロックを解除する必要がある Exchange Online の管理された可用性監視プローブでも使用されます。

BitLocker で保護されたボリュームは、ボリューム全体の暗号化キーで暗号化され、ボリューム マスター キーで暗号化されます。 BitLocker では、FIPS に準拠したアルゴリズムを使用して、暗号化キーがクリアでネットワーク経由で保存または送信されないようにします。 Microsoft 365 による保管中の顧客データ保護の実装は、既定の BitLocker の実装から逸脱するのものではありません。
