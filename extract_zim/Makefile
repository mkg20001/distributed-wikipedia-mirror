all: extract_zim

extract_zim: zim/target/release/extract_zim
	cp -f $< $@

ZIM_FILES=$(wildcard zim/src/*) zim/extract_zim.rs zim/Cargo.toml

zim/target/release/extract_zim: $(ZIM_FILES)
	(cd zim && cargo build --release --bin extract_zim)

$(ZIM_FILES): git-submodules

git-submodules:
	git submodule update --init

