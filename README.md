# ALICE-Text SaaS

Exception-based text compression API

## License

AGPL-3.0

## Architecture

```
Frontend :3000  -->  API Gateway :8080  -->  Core Engine :8081
```

| Layer | Port | Technology |
|-------|------|-----------|
| Frontend | 3000 | Next.js 14, Tailwind CSS |
| API Gateway | 8080 | Rust, Axum |
| Core Engine | 8081 | Rust, Axum, ALICE-Text |

## Endpoints

| Method | Path | Description |
|--------|------|-------------|
| `POST /api/v1/compress` | テキスト圧縮 |
| `POST /api/v1/decompress` | テキスト復元 |
| `GET  /api/v1/stats` | 圧縮統計情報 |
| `GET`  | `/health` | ヘルスチェック |

## Quick Start

```bash
cd services/core-engine
cargo run --release
curl http://localhost:8081/health
```

## Author

Moroya Sakamoto
